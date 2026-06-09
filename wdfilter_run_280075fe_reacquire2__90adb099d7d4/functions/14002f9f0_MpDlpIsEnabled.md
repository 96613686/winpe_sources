# MpDlpIsEnabled

- ea: `0x14002f9f0`
- end: `0x14002fdf3`
- name: `MpDlpIsEnabled`
- size: `1027`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002080`
- `0x140030380`
- `0x14006ddd0`
- `0x14006de7c`
- `0x14006e7d0`
- `0x14006f0d8`
- `0x1400762f4`
- `0x140082380`
- `0x140085dd0`
- `0x140085e50`
- `0x140085ed0`

## callees

- `0x140002450`
- `0x1400118d0`
- `0x14002f9f0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003a2c0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002fb97`
- `ntoskrnl!PsGetProcessId` at `0x14002fb97`
- `ntoskrnl!ExGetPreviousMode` at `0x14002fd37`
- `ntoskrnl!ExGetPreviousMode` at `0x14002fd37`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fd11`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fde2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fd11`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fde2`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002fb4e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002fb4e`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002faf0`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002fd70`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002fb85`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002fb85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002fc50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002fc50`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002fc44`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002fc44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002fbcd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002fbcd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fbbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fbbb`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002fa18`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002fdac`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002fa18`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002fdac`
- `ntoskrnl!IoThreadToProcess` at `0x14002faa6`
- `ntoskrnl!IoThreadToProcess` at `0x14002fad2`
- `ntoskrnl!IoThreadToProcess` at `0x14002faa6`
- `ntoskrnl!IoThreadToProcess` at `0x14002fad2`

## pseudocode

```c
bool __fastcall MpDlpIsEnabled(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  struct _KPROCESS *CurrentProcess; // rbp
  struct _KPROCESS *v7; // rbx
  struct _KPROCESS *v8; // rbx
  _QWORD *v9; // rbp
  _QWORD *v10; // r15
  PACCESS_TOKEN v11; // rax
  void *v12; // rbx
  struct _KPROCESS *RequestorProcess; // rbx
  LONGLONG TimeQuadPart; // r12
  unsigned __int64 ProcessId; // rdi
  int v16; // esi
  char *v17; // rbx
  _QWORD *v18; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v20; // rcx
  bool v21; // bl
  __int64 v22; // rcx
  __int64 v23; // rcx
  struct _KPROCESS *v24; // rax
  int ProcessContextByObject; // eax
  _QWORD *v26; // [rsp+20h] [rbp-48h]
  _QWORD *v27; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+31h] [rbp-37h] BYREF
  _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+34h] [rbp-34h] BYREF

  v4 = a1;
  CurrentProcess = IoGetCurrentProcess();
  if ( !MpDlpData )
    return 0;
  if ( (unsigned __int64)(v4 - 1) <= 1 )
    v4 = 0;
  if ( !*((_BYTE *)MpDlpData + 32)
    || (*(_DWORD *)(MpData + 864) & 0x400) == 0
    || !*(_QWORD *)(MpData + 320) && !*(_QWORD *)(MpData + 336) )
  {
    return 0;
  }
  v7 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v7
    || (v8 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v8) )
  {
    if ( a1 == 1 )
      return 1;
    return a1 == 2;
  }
  else
  {
    if ( v4 )
    {
      CurrentProcess = (struct _KPROCESS *)MpGetRequestorProcess(v4);
      if ( !CurrentProcess )
        return 0;
    }
    if ( PsInitialSystemProcess == CurrentProcess )
    {
      if ( !v4
        || ExGetPreviousMode()
        || (PEPROCESS)MpGetRequestorProcess(v4) != PsInitialSystemProcess
        || (v22 = *(_QWORD *)(v4 + 16), (*(_BYTE *)(v22 + 6) & 1) == 0)
        || (v23 = *(_QWORD *)(*(_QWORD *)(v22 + 24) + 8LL), !*(_QWORD *)(v23 + 32))
        || *(int *)(v23 + 40) < 2 )
      {
        if ( a1 != 2 )
          return 0;
      }
    }
    v9 = a2;
    if ( a2 )
    {
LABEL_30:
      v21 = (v9[7] & 0x40000000) != 0 || *((_DWORD *)v9 + 60) == 33;
      if ( v9 != a2 )
        MpReleaseProcessContext(v9);
      return !v21;
    }
    if ( !v4 )
      return 1;
    CopyOnOpen[0] = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    v10 = 0;
    v26 = 0;
    v11 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
    v12 = v11;
    if ( v11 )
    {
      v27 = 0;
      if ( (int)MpDlpGetProcessContextFromTokenAttribute(v11, &v27) < 0 )
      {
        PsDereferenceImpersonationToken(v12);
      }
      else
      {
        v9 = v27;
        PsDereferenceImpersonationToken(v12);
        if ( v9 )
          goto LABEL_30;
      }
    }
    RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(v4);
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
    v16 = -1073741275;
    if ( ProcessId )
    {
      v17 = (char *)MpProcessTable;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v17 + 8), 1u);
      v18 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
      for ( i = (_QWORD *)*v18; i != v18; i = (_QWORD *)*i )
      {
        v20 = (volatile signed __int32 *)(i - 1);
        if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v20 + 4) )
        {
          _InterlockedIncrement(v20 + 12);
          v10 = i - 1;
          v26 = i - 1;
          v16 = 0;
          break;
        }
      }
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
    }
    if ( v16 < 0 || !v10 )
    {
      v24 = IoGetCurrentProcess();
      ProcessContextByObject = MpGetProcessContextByObject(v24);
      v10 = v26;
      v16 = ProcessContextByObject;
      if ( !v26 )
      {
        if ( ProcessContextByObject < 0 )
          return 1;
        goto LABEL_29;
      }
    }
    if ( v16 >= 0 )
    {
      v9 = v10;
LABEL_29:
      if ( v9 )
        goto LABEL_30;
      return 1;
    }
    MpReleaseProcessContext(v10);
    return 1;
  }
}

```

## disassembly

```asm
0x14002f9f0  mov     [rsp+arg_18], rbx
0x14002f9f5  push    rbp
0x14002f9f6  push    rsi
0x14002f9f7  push    rdi
0x14002f9f8  push    r14
0x14002f9fa  push    r15
0x14002f9fc  sub     rsp, 40h
0x14002fa00  mov     rax, cs:__security_cookie
0x14002fa07  xor     rax, rsp
0x14002fa0a  mov     [rsp+68h+var_30], rax
0x14002fa0f  mov     r14, rdx
0x14002fa12  mov     rsi, rcx
0x14002fa15  mov     rdi, rcx
0x14002fa18  call    cs:__imp_IoGetCurrentProcess
0x14002fa1f  nop     dword ptr [rax+rax+00h]
0x14002fa24  mov     r8, cs:MpDlpData
0x14002fa2b  mov     rbp, rax
0x14002fa2e  test    r8, r8
0x14002fa31  jz      short loc_14002FA4A
0x14002fa33  lea     rdx, [rdi-1]
0x14002fa37  cmp     rdx, 1
0x14002fa3b  jbe     loc_14002FD69
0x14002fa41  movzx   ecx, byte ptr [r8+20h]
0x14002fa46  test    cl, cl
0x14002fa48  jnz     short loc_14002FA6E
0x14002fa4a  xor     al, al
0x14002fa4c  mov     rcx, [rsp+68h+var_30]
0x14002fa51  xor     rcx, rsp; StackCookie
0x14002fa54  call    __security_check_cookie
0x14002fa59  mov     rbx, [rsp+68h+arg_18]
0x14002fa61  add     rsp, 40h
0x14002fa65  pop     r15
0x14002fa67  pop     r14
0x14002fa69  pop     rdi
0x14002fa6a  pop     rsi
0x14002fa6b  pop     rbp
0x14002fa6c  retn
0x14002fa6e  mov     rcx, cs:MpData
0x14002fa75  test    dword ptr [rcx+360h], 400h
0x14002fa7f  jz      short loc_14002FA4A
0x14002fa81  cmp     qword ptr [rcx+140h], 0
0x14002fa89  jz      loc_14002FD56
0x14002fa8f  mov     rcx, gs:188h; Thread
0x14002fa98  mov     rax, cs:MpData
0x14002fa9f  mov     rbx, [rax+0E8h]
0x14002faa6  call    cs:__imp_IoThreadToProcess
0x14002faad  nop     dword ptr [rax+rax+00h]
0x14002fab2  cmp     rax, rbx
0x14002fab5  jz      loc_14002FC14
0x14002fabb  mov     rcx, gs:188h; Thread
0x14002fac4  mov     rax, cs:MpData
0x14002facb  mov     rbx, [rax+100h]
0x14002fad2  call    cs:__imp_IoThreadToProcess
0x14002fad9  nop     dword ptr [rax+rax+00h]
0x14002fade  cmp     rax, rbx
0x14002fae1  jz      loc_14002FC14
0x14002fae7  test    rdi, rdi
0x14002faea  jnz     loc_14002FCC3
0x14002faf0  mov     rax, cs:__imp_PsInitialSystemProcess
0x14002faf7  cmp     [rax], rbp
0x14002fafa  jz      loc_14002FD32
0x14002fb00  mov     rbp, r14
0x14002fb03  test    r14, r14
0x14002fb06  jnz     loc_14002FC8D
0x14002fb0c  test    rdi, rdi
0x14002fb0f  jz      loc_14002FC1E
0x14002fb15  test    r14, r14
0x14002fb18  jnz     loc_14002FC8D
0x14002fb1e  xor     esi, esi
0x14002fb20  lea     r9, [rsp+68h+ImpersonationLevel]; ImpersonationLevel
0x14002fb25  mov     [rsp+68h+CopyOnOpen], sil
0x14002fb2a  lea     r8, [rsp+68h+EffectiveOnly]; EffectiveOnly
0x14002fb2f  mov     [rsp+68h+EffectiveOnly], sil
0x14002fb34  lea     rdx, [rsp+68h+CopyOnOpen]; CopyOnOpen
0x14002fb39  mov     [rsp+68h+ImpersonationLevel], esi
0x14002fb3d  xor     r15d, r15d
0x14002fb40  mov     rcx, gs:188h; Thread
0x14002fb49  mov     [rsp+68h+var_48], r15
0x14002fb4e  call    cs:__imp_PsReferenceImpersonationToken
0x14002fb55  nop     dword ptr [rax+rax+00h]
0x14002fb5a  mov     rbx, rax
0x14002fb5d  test    rax, rax
0x14002fb60  jnz     loc_14002FCED
0x14002fb66  test    rdi, rdi
0x14002fb69  jz      loc_14002FC64
0x14002fb6f  mov     rcx, rdi
0x14002fb72  mov     [rsp+68h+arg_10], r12
0x14002fb7a  call    MpGetRequestorProcess
0x14002fb7f  mov     rcx, rax; Process
0x14002fb82  mov     rbx, rax
0x14002fb85  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002fb8c  nop     dword ptr [rax+rax+00h]
0x14002fb91  mov     rcx, rbx; Process
0x14002fb94  mov     r12, rax
0x14002fb97  call    cs:__imp_PsGetProcessId
0x14002fb9e  nop     dword ptr [rax+rax+00h]
0x14002fba3  mov     rdi, rax
0x14002fba6  mov     esi, 0C0000225h
0x14002fbab  test    rax, rax
0x14002fbae  jz      loc_14002FC5C
0x14002fbb4  mov     rbx, cs:MpProcessTable
0x14002fbbb  call    cs:__imp_KeEnterCriticalRegion
0x14002fbc2  nop     dword ptr [rax+rax+00h]
0x14002fbc7  mov     dl, 1; Wait
0x14002fbc9  lea     rcx, [rbx+8]; Resource
0x14002fbcd  call    cs:__imp_ExAcquireResourceSharedLite
0x14002fbd4  nop     dword ptr [rax+rax+00h]
0x14002fbd9  mov     rax, cs:MpProcessTable
0x14002fbe0  mov     r8, rdi
0x14002fbe3  shr     r8, 2
0x14002fbe7  and     r8d, 7Fh
0x14002fbeb  shl     r8, 4
0x14002fbef  add     r8, [rax+180h]
0x14002fbf6  mov     rax, [r8]
0x14002fbf9  nop     dword ptr [rax+00000000h]
0x14002fc00  cmp     rax, r8
0x14002fc03  jz      short loc_14002FC39
0x14002fc05  cmp     rdi, [rax+10h]
0x14002fc09  lea     rcx, [rax-8]
0x14002fc0d  jz      short loc_14002FC25
0x14002fc0f  mov     rax, [rax]
0x14002fc12  jmp     short loc_14002FC00
0x14002fc14  cmp     rsi, 1
0x14002fc18  jnz     loc_14002FCDC
0x14002fc1e  mov     al, 1
0x14002fc20  jmp     loc_14002FA4C
0x14002fc25  cmp     r12, [rcx+20h]
0x14002fc29  jnz     short loc_14002FC0F
0x14002fc2b  lock inc dword ptr [rcx+30h]
0x14002fc2f  mov     r15, rcx
0x14002fc32  mov     [rsp+68h+var_48], rcx
0x14002fc37  xor     esi, esi
0x14002fc39  mov     rcx, cs:MpProcessTable
0x14002fc40  add     rcx, 8; Resource
0x14002fc44  call    cs:__imp_ExReleaseResourceLite
0x14002fc4b  nop     dword ptr [rax+rax+00h]
0x14002fc50  call    cs:__imp_KeLeaveCriticalRegion
0x14002fc57  nop     dword ptr [rax+rax+00h]
0x14002fc5c  mov     r12, [rsp+68h+arg_10]
0x14002fc64  test    esi, esi
0x14002fc66  js      loc_14002FDAC
0x14002fc6c  test    r15, r15
0x14002fc6f  jz      loc_14002FDAC
0x14002fc75  test    esi, esi
0x14002fc77  jns     short loc_14002FCE8
0x14002fc79  mov     rcx, r15
0x14002fc7c  call    MpReleaseProcessContext
0x14002fc81  mov     al, 1
0x14002fc83  jmp     loc_14002FA4C
0x14002fc88  test    rbp, rbp
0x14002fc8b  jz      short loc_14002FC1E
0x14002fc8d  test    dword ptr [rbp+38h], 40000000h
0x14002fc94  jnz     loc_14002FD2B
0x14002fc9a  cmp     dword ptr [rbp+0F0h], 21h ; '!'
0x14002fca1  jz      loc_14002FD2B
0x14002fca7  xor     bl, bl
0x14002fca9  cmp     rbp, r14
0x14002fcac  jz      short loc_14002FCB6
0x14002fcae  mov     rcx, rbp
0x14002fcb1  call    MpReleaseProcessContext
0x14002fcb6  test    bl, bl
0x14002fcb8  jnz     loc_14002FA4A
0x14002fcbe  jmp     loc_14002FC1E
0x14002fcc3  mov     rcx, rdi
0x14002fcc6  call    MpGetRequestorProcess
0x14002fccb  mov     rbp, rax
0x14002fcce  test    rax, rax
0x14002fcd1  jz      loc_14002FA4A
0x14002fcd7  jmp     loc_14002FAF0
0x14002fcdc  cmp     rsi, 2
0x14002fce0  setz    al
0x14002fce3  jmp     loc_14002FA4C
0x14002fce8  mov     rbp, r15
0x14002fceb  jmp     short loc_14002FC88
0x14002fced  lea     rdx, [rsp+68h+var_40]
0x14002fcf2  mov     [rsp+68h+var_40], rsi
0x14002fcf7  mov     rcx, rbx
0x14002fcfa  call    MpDlpGetProcessContextFromTokenAttribute
0x14002fcff  mov     esi, eax
0x14002fd01  mov     rcx, rbx; ImpersonationToken
0x14002fd04  test    eax, eax
0x14002fd06  js      loc_14002FDE2
0x14002fd0c  mov     rbp, [rsp+68h+var_40]
0x14002fd11  call    cs:__imp_PsDereferenceImpersonationToken
0x14002fd18  nop     dword ptr [rax+rax+00h]
0x14002fd1d  test    rbp, rbp
0x14002fd20  jnz     loc_14002FC8D
0x14002fd26  jmp     loc_14002FB66
0x14002fd2b  mov     bl, 1
0x14002fd2d  jmp     loc_14002FCA9
0x14002fd32  test    rdi, rdi
0x14002fd35  jz      short loc_14002FD47
0x14002fd37  call    cs:__imp_ExGetPreviousMode
0x14002fd3e  nop     dword ptr [rax+rax+00h]
0x14002fd43  test    al, al
0x14002fd45  jz      short loc_14002FD70
0x14002fd47  cmp     rsi, 2
0x14002fd4b  jnz     loc_14002FA4A
0x14002fd51  jmp     loc_14002FB00
0x14002fd56  cmp     qword ptr [rcx+150h], 0
0x14002fd5e  jnz     loc_14002FA8F
0x14002fd64  jmp     loc_14002FA4A
0x14002fd69  xor     edi, edi
0x14002fd6b  jmp     loc_14002FA41
0x14002fd70  mov     rax, cs:__imp_PsInitialSystemProcess
0x14002fd77  mov     rcx, rdi
0x14002fd7a  mov     rbx, [rax]
0x14002fd7d  call    MpGetRequestorProcess
0x14002fd82  cmp     rax, rbx
0x14002fd85  jnz     short loc_14002FD47
0x14002fd87  mov     rcx, [rdi+10h]
0x14002fd8b  test    byte ptr [rcx+6], 1
0x14002fd8f  jz      short loc_14002FD47
0x14002fd91  mov     rax, [rcx+18h]
0x14002fd95  mov     rcx, [rax+8]
0x14002fd99  cmp     qword ptr [rcx+20h], 0
0x14002fd9e  jz      short loc_14002FD47
0x14002fda0  cmp     dword ptr [rcx+28h], 2
0x14002fda4  jge     loc_14002FB00
0x14002fdaa  jmp     short loc_14002FD47
0x14002fdac  call    cs:__imp_IoGetCurrentProcess
0x14002fdb3  nop     dword ptr [rax+rax+00h]
0x14002fdb8  mov     rcx, rax; Process
0x14002fdbb  lea     rdx, [rsp+68h+var_48]
0x14002fdc0  call    MpGetProcessContextByObject
0x14002fdc5  mov     r15, [rsp+68h+var_48]
0x14002fdca  mov     esi, eax
0x14002fdcc  test    r15, r15
0x14002fdcf  jnz     loc_14002FC75
0x14002fdd5  test    eax, eax
0x14002fdd7  js      loc_14002FC1E
0x14002fddd  jmp     loc_14002FC88
0x14002fde2  call    cs:__imp_PsDereferenceImpersonationToken
0x14002fde9  nop     dword ptr [rax+rax+00h]
0x14002fdee  jmp     loc_14002FB66
```
