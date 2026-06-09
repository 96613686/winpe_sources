# MpDlpGetAccessCheckProcessContext

- ea: `0x140039f70`
- end: `0x14003a1a1`
- name: `MpDlpGetAccessCheckProcessContext`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400393f0`

## callees

- `0x140002450`
- `0x1400118d0`
- `0x140030060`
- `0x140039f70`
- `0x14003a1b0`
- `0x14003a2c0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14003a016`
- `ntoskrnl!PsGetProcessId` at `0x14003a016`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003a120`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003a17d`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003a120`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003a17d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140039fd5`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140039fd5`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003a004`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003a004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a0b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a0b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a0ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a0ac`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a04c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a04c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a03a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a03a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a13a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a13a`

## pseudocode

```c
__int64 __fastcall MpDlpGetAccessCheckProcessContext(__int64 a1, _QWORD *a2)
{
  int ProcessContextFromTokenAttribute; // esi
  _QWORD *v5; // r14
  PACCESS_TOKEN v6; // rax
  void *v7; // rbp
  struct _KPROCESS *RequestorProcess; // rbx
  LONGLONG TimeQuadPart; // rbp
  unsigned __int64 ProcessId; // rdi
  char *v11; // rbx
  _QWORD *v12; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v14; // rcx
  __int64 v16; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  _QWORD *v18; // [rsp+20h] [rbp-48h]
  __int64 v19; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int8 v20; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 v21[3]; // [rsp+31h] [rbp-37h] BYREF
  int v22; // [rsp+34h] [rbp-34h] BYREF

  v18 = 0;
  ProcessContextFromTokenAttribute = 0;
  v21[0] = 0;
  v20 = 0;
  v5 = 0;
  v22 = 0;
  if ( a2 )
  {
    v6 = PsReferenceImpersonationToken(KeGetCurrentThread(), v21, &v20, (PSECURITY_IMPERSONATION_LEVEL)&v22);
    v7 = v6;
    if ( v6 )
    {
      v19 = 0;
      ProcessContextFromTokenAttribute = MpDlpGetProcessContextFromTokenAttribute(v6, &v19);
      if ( ProcessContextFromTokenAttribute < 0 )
      {
        PsDereferenceImpersonationToken(v7);
      }
      else
      {
        v16 = v19;
        *a2 = v19;
        PsDereferenceImpersonationToken(v7);
        if ( v16 )
        {
          _mm_lfence();
          return (unsigned int)ProcessContextFromTokenAttribute;
        }
      }
    }
    if ( a1 )
    {
      RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
      ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
      ProcessContextFromTokenAttribute = -1073741275;
      if ( ProcessId )
      {
        v11 = (char *)MpProcessTable;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v11 + 8), 1u);
        v12 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
        for ( i = (_QWORD *)*v12; i != v12; i = (_QWORD *)*i )
        {
          v14 = (volatile signed __int32 *)(i - 1);
          if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v14 + 4) )
          {
            _InterlockedIncrement(v14 + 12);
            v5 = i - 1;
            v18 = i - 1;
            ProcessContextFromTokenAttribute = 0;
            break;
          }
        }
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
      }
    }
    if ( ProcessContextFromTokenAttribute >= 0 && v5 )
      goto LABEL_14;
    CurrentProcess = IoGetCurrentProcess();
    ProcessContextFromTokenAttribute = MpGetProcessContextByObject(CurrentProcess);
    if ( ProcessContextFromTokenAttribute < 0 )
    {
      if ( v18 )
        MpReleaseProcessContext(v18);
      return (unsigned int)ProcessContextFromTokenAttribute;
    }
    v5 = v18;
    if ( v18 )
LABEL_14:
      *a2 = v5;
    return (unsigned int)ProcessContextFromTokenAttribute;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140039f70  mov     r11, rsp
0x140039f73  push    rsi
0x140039f74  push    rdi
0x140039f75  push    r12
0x140039f77  push    r14
0x140039f79  push    r15
0x140039f7b  sub     rsp, 40h
0x140039f7f  mov     rax, cs:__security_cookie
0x140039f86  xor     rax, rsp
0x140039f89  mov     [rsp+68h+var_30], rax
0x140039f8e  xor     r12d, r12d
0x140039f91  mov     r15, rdx
0x140039f94  mov     [r11-48h], r12
0x140039f98  mov     esi, r12d
0x140039f9b  mov     [rsp+68h+var_37], sil
0x140039fa0  mov     rdi, rcx
0x140039fa3  mov     [rsp+68h+var_38], sil
0x140039fa8  mov     r14d, r12d
0x140039fab  mov     [r11-34h], r12d
0x140039faf  test    rdx, rdx
0x140039fb2  jz      loc_14003A173
0x140039fb8  mov     rcx, gs:188h; Thread
0x140039fc1  lea     r9, [r11-34h]; ImpersonationLevel
0x140039fc5  mov     [r11+18h], rbx
0x140039fc9  lea     r8, [r11-38h]; EffectiveOnly
0x140039fcd  lea     rdx, [r11-37h]; CopyOnOpen
0x140039fd1  mov     [r11+20h], rbp
0x140039fd5  call    cs:__imp_PsReferenceImpersonationToken
0x140039fdc  nop     dword ptr [rax+rax+00h]
0x140039fe1  mov     rbp, rax
0x140039fe4  test    rax, rax
0x140039fe7  jnz     loc_14003A0FD
0x140039fed  test    rdi, rdi
0x140039ff0  jz      loc_14003A0C4
0x140039ff6  mov     rcx, rdi
0x140039ff9  call    MpGetRequestorProcess
0x140039ffe  mov     rcx, rax; Process
0x14003a001  mov     rbx, rax
0x14003a004  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003a00b  nop     dword ptr [rax+rax+00h]
0x14003a010  mov     rcx, rbx; Process
0x14003a013  mov     rbp, rax
0x14003a016  call    cs:__imp_PsGetProcessId
0x14003a01d  nop     dword ptr [rax+rax+00h]
0x14003a022  mov     rdi, rax
0x14003a025  mov     esi, 0C0000225h
0x14003a02a  test    rax, rax
0x14003a02d  jz      loc_14003A0C4
0x14003a033  mov     rbx, cs:MpProcessTable
0x14003a03a  call    cs:__imp_KeEnterCriticalRegion
0x14003a041  nop     dword ptr [rax+rax+00h]
0x14003a046  mov     dl, 1; Wait
0x14003a048  lea     rcx, [rbx+8]; Resource
0x14003a04c  call    cs:__imp_ExAcquireResourceSharedLite
0x14003a053  nop     dword ptr [rax+rax+00h]
0x14003a058  mov     rax, cs:MpProcessTable
0x14003a05f  mov     r8, rdi
0x14003a062  shr     r8, 2
0x14003a066  and     r8d, 7Fh
0x14003a06a  shl     r8, 4
0x14003a06e  add     r8, [rax+180h]
0x14003a075  mov     rax, [r8]
0x14003a078  cmp     rax, r8
0x14003a07b  jz      short loc_14003A0A1
0x14003a07d  cmp     rdi, [rax+10h]
0x14003a081  lea     rcx, [rax-8]
0x14003a085  jz      short loc_14003A08C
0x14003a087  mov     rax, [rax]
0x14003a08a  jmp     short loc_14003A078
0x14003a08c  cmp     rbp, [rcx+20h]
0x14003a090  jnz     short loc_14003A087
0x14003a092  lock inc dword ptr [rcx+30h]
0x14003a096  mov     r14, rcx
0x14003a099  mov     [rsp+68h+var_48], rcx
0x14003a09e  mov     esi, r12d
0x14003a0a1  mov     rcx, cs:MpProcessTable
0x14003a0a8  add     rcx, 8; Resource
0x14003a0ac  call    cs:__imp_ExReleaseResourceLite
0x14003a0b3  nop     dword ptr [rax+rax+00h]
0x14003a0b8  call    cs:__imp_KeLeaveCriticalRegion
0x14003a0bf  nop     dword ptr [rax+rax+00h]
0x14003a0c4  test    esi, esi
0x14003a0c6  js      short loc_14003A13A
0x14003a0c8  test    r14, r14
0x14003a0cb  jz      short loc_14003A13A
0x14003a0cd  mov     [r15], r14
0x14003a0d0  mov     rbx, [rsp+68h+arg_10]
0x14003a0d8  mov     eax, esi
0x14003a0da  mov     rbp, [rsp+68h+arg_18]
0x14003a0e2  mov     rcx, [rsp+68h+var_30]
0x14003a0e7  xor     rcx, rsp; StackCookie
0x14003a0ea  call    __security_check_cookie
0x14003a0ef  add     rsp, 40h
0x14003a0f3  pop     r15
0x14003a0f5  pop     r14
0x14003a0f7  pop     r12
0x14003a0f9  pop     rdi
0x14003a0fa  pop     rsi
0x14003a0fb  retn
0x14003a0fd  lea     rdx, [rsp+68h+var_40]
0x14003a102  mov     [rsp+68h+var_40], r12
0x14003a107  mov     rcx, rbp
0x14003a10a  call    MpDlpGetProcessContextFromTokenAttribute
0x14003a10f  mov     esi, eax
0x14003a111  mov     rcx, rbp; ImpersonationToken
0x14003a114  test    eax, eax
0x14003a116  js      short loc_14003A17D
0x14003a118  mov     rbx, [rsp+68h+var_40]
0x14003a11d  mov     [r15], rbx
0x14003a120  call    cs:__imp_PsDereferenceImpersonationToken
0x14003a127  nop     dword ptr [rax+rax+00h]
0x14003a12c  test    rbx, rbx
0x14003a12f  jz      loc_140039FED
0x14003a135  lfence
0x14003a138  jmp     short loc_14003A0D0
0x14003a13a  call    cs:__imp_IoGetCurrentProcess
0x14003a141  nop     dword ptr [rax+rax+00h]
0x14003a146  mov     rcx, rax; Process
0x14003a149  lea     rdx, [rsp+68h+var_48]
0x14003a14e  call    MpGetProcessContextByObject
0x14003a153  mov     ebx, eax
0x14003a155  mov     esi, eax
0x14003a157  test    eax, eax
0x14003a159  jns     short loc_14003A18E
0x14003a15b  mov     rcx, [rsp+68h+var_48]
0x14003a160  test    rcx, rcx
0x14003a163  jz      loc_14003A0D0
0x14003a169  call    MpReleaseProcessContext
0x14003a16e  jmp     loc_14003A0D0
0x14003a173  mov     eax, 0C000000Dh
0x14003a178  jmp     loc_14003A0E2
0x14003a17d  call    cs:__imp_PsDereferenceImpersonationToken
0x14003a184  nop     dword ptr [rax+rax+00h]
0x14003a189  jmp     loc_140039FED
0x14003a18e  mov     r14, [rsp+68h+var_48]
0x14003a193  test    r14, r14
0x14003a196  jz      loc_14003A0D0
0x14003a19c  jmp     loc_14003A0CD
```
