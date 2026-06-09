# AddUserToHandle(void *,void *,ulong)

- ea: `0x18005200c`
- end: `0x18005220a`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e2830`

## callees

- `0x1800512e0`
- `0x18005200c`
- `0x180052210`
- `0x1800e2bc4`
- `0x1800e34bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800521bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800521dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800521bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800521dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052085`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800521ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800521eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800521ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800521eb`
- `ntdll!NtSetSecurityObject` at `0x18005218f`
- `ntdll!NtSetSecurityObject` at `0x18005218f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800520f4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800520f4`
- `ntdll!NtQuerySecurityObject` at `0x18005203f`
- `ntdll!NtQuerySecurityObject` at `0x1800520cb`
- `ntdll!NtQuerySecurityObject` at `0x18005203f`
- `ntdll!NtQuerySecurityObject` at `0x1800520cb`

## string_xrefs

- `0x180052054`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180052097`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180052107`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180052146`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18005219d`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall AddUserToHandle(HANDLE Handle, void *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  ULONG v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdi
  HANDLE v17; // rax
  NTSTATUS v18; // eax
  unsigned int v19; // eax
  void *v20; // rbx
  unsigned int v21; // edi
  HANDLE v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  int LengthNeeded; // [rsp+20h] [rbp-48h]
  int LengthNeededa; // [rsp+20h] [rbp-48h]
  int LengthNeededb; // [rsp+20h] [rbp-48h]
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  bool v32; // [rsp+B8h] [rbp+50h] BYREF

  Length = 0;
  v6 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v6 == -1073741789 )
  {
    v8 = Length;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 0, v8);
    if ( !v10 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
        (const char *)0x8007000ELL,
        LengthNeeded);
      return v11;
    }
    v12 = NtQuerySecurityObject(Handle, 4u, v10, Length, &Length);
    if ( v12 >= 0 )
    {
      lpMem = 0;
      memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v12 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v12 >= 0 )
      {
        v32 = 0;
        v15 = BuildUserSD(v10, a2, a3, &v32, SecurityDescriptor);
        v11 = v15;
        if ( v15 >= 0 )
        {
          if ( v32 || (v18 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor), v18 >= 0) )
          {
            v23 = lpMem;
            if ( lpMem )
            {
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v23);
            }
            v11 = 0;
          }
          else
          {
            v19 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x79,
                    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                    (const char *)(unsigned int)v18,
                    LengthNeededb);
            v20 = lpMem;
            v21 = v19;
            if ( lpMem )
            {
              v22 = GetProcessHeap();
              HeapFree(v22, 0, v20);
            }
            v11 = v21;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v15,
            LengthNeededb);
          v16 = lpMem;
          if ( lpMem )
          {
            v17 = GetProcessHeap();
            HeapFree(v17, 0, v16);
          }
        }
        goto LABEL_23;
      }
      v13 = 108;
    }
    else
    {
      v13 = 105;
    }
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v12,
            LengthNeededa);
LABEL_23:
    wil::details::FreeProcessHeap((wil::details *)v10, v14);
    return v11;
  }
  if ( v6 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x62,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)v6,
             LengthNeeded);
}

```

## disassembly

```asm
0x18005200c  push    rbp
0x18005200e  push    rbx
0x18005200f  push    rsi
0x180052010  push    rdi
0x180052011  push    r14
0x180052013  push    r15
0x180052015  mov     rbp, rsp
0x180052018  sub     rsp, 68h
0x18005201c  xor     r9d, r9d; Length
0x18005201f  mov     [rbp+Length], 0
0x180052026  mov     r14d, r8d
0x180052029  lea     rax, [rbp+Length]
0x18005202d  mov     r15, rdx
0x180052030  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180052035  xor     r8d, r8d; SecurityDescriptor
0x180052038  mov     rdi, rcx
0x18005203b  lea     edx, [r9+4]; SecurityInformation
0x18005203f  call    cs:__imp_NtQuerySecurityObject
0x180052045  cmp     eax, 0C0000023h
0x18005204a  jz      short loc_180052074
0x18005204c  test    eax, eax
0x18005204e  jns     short loc_18005206D
0x180052050  mov     rcx, [rbp+30h]; this
0x180052054  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005205b  mov     r9d, eax; char *
0x18005205e  mov     edx, 62h ; 'b'; void *
0x180052063  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180052068  jmp     loc_1800521FD
0x18005206d  xor     eax, eax
0x18005206f  jmp     loc_1800521FD
0x180052074  mov     ebx, [rbp+Length]
0x180052077  call    cs:__imp_GetProcessHeap
0x18005207d  mov     r8d, ebx; dwBytes
0x180052080  xor     edx, edx; dwFlags
0x180052082  mov     rcx, rax; hHeap
0x180052085  call    cs:__imp_HeapAlloc
0x18005208b  mov     rsi, rax
0x18005208e  test    rax, rax
0x180052091  jnz     short loc_1800520B3
0x180052093  mov     rcx, [rbp+30h]; this
0x180052097  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005209e  mov     ebx, 8007000Eh
0x1800520a3  lea     edx, [rax+66h]; void *
0x1800520a6  mov     r9d, ebx; char *
0x1800520a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800520ae  jmp     loc_1800521FB
0x1800520b3  mov     r9d, [rbp+Length]; Length
0x1800520b7  lea     rax, [rbp+Length]
0x1800520bb  mov     r8, rsi; SecurityDescriptor
0x1800520be  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x1800520c3  mov     edx, 4; SecurityInformation
0x1800520c8  mov     rcx, rdi; Handle
0x1800520cb  call    cs:__imp_NtQuerySecurityObject
0x1800520d1  test    eax, eax
0x1800520d3  jns     short loc_1800520DC
0x1800520d5  mov     edx, 69h ; 'i'
0x1800520da  jmp     short loc_180052103
0x1800520dc  xor     eax, eax
0x1800520de  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800520e2  xorps   xmm0, xmm0
0x1800520e5  mov     [rbp+lpMem], rax
0x1800520e9  movups  [rbp+SecurityDescriptor], xmm0
0x1800520ed  lea     edx, [rax+1]; Revision
0x1800520f0  movups  [rbp+var_20], xmm0
0x1800520f4  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800520fa  test    eax, eax
0x1800520fc  jns     short loc_18005211D
0x1800520fe  mov     edx, 6Ch ; 'l'; void *
0x180052103  mov     rcx, [rbp+30h]; this
0x180052107  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005210e  mov     r9d, eax; char *
0x180052111  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180052116  mov     ebx, eax
0x180052118  jmp     loc_1800521F3
0x18005211d  lea     rax, [rbp+SecurityDescriptor]
0x180052121  mov     [rbp+arg_18], 0
0x180052125  lea     r9, [rbp+arg_18]; bool *
0x180052129  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x18005212e  mov     r8d, r14d; unsigned int
0x180052131  mov     rdx, r15; void *
0x180052134  mov     rcx, rsi; void *
0x180052137  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x18005213c  mov     ebx, eax
0x18005213e  test    eax, eax
0x180052140  jns     short loc_18005217D
0x180052142  mov     rcx, [rbp+30h]; this
0x180052146  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005214d  mov     r9d, eax; char *
0x180052150  mov     edx, 72h ; 'r'; void *
0x180052155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005215a  mov     rdi, [rbp+lpMem]
0x18005215e  test    rdi, rdi
0x180052161  jz      loc_1800521F3
0x180052167  call    cs:__imp_GetProcessHeap
0x18005216d  mov     r8, rdi; lpMem
0x180052170  xor     edx, edx; dwFlags
0x180052172  mov     rcx, rax; hHeap
0x180052175  call    cs:__imp_HeapFree
0x18005217b  jmp     short loc_1800521F3
0x18005217d  cmp     [rbp+arg_18], 0
0x180052181  jnz     short loc_1800521D4
0x180052183  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180052187  mov     edx, 4; SecurityInformation
0x18005218c  mov     rcx, rdi; Handle
0x18005218f  call    cs:__imp_NtSetSecurityObject
0x180052195  test    eax, eax
0x180052197  jns     short loc_1800521D4
0x180052199  mov     rcx, [rbp+30h]; this
0x18005219d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800521a4  mov     r9d, eax; char *
0x1800521a7  mov     edx, 79h ; 'y'; void *
0x1800521ac  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800521b1  mov     rbx, [rbp+lpMem]
0x1800521b5  mov     edi, eax
0x1800521b7  test    rbx, rbx
0x1800521ba  jz      short loc_1800521D0
0x1800521bc  call    cs:__imp_GetProcessHeap
0x1800521c2  mov     r8, rbx; lpMem
0x1800521c5  xor     edx, edx; dwFlags
0x1800521c7  mov     rcx, rax; hHeap
0x1800521ca  call    cs:__imp_HeapFree
0x1800521d0  mov     ebx, edi
0x1800521d2  jmp     short loc_1800521F3
0x1800521d4  mov     rbx, [rbp+lpMem]
0x1800521d8  test    rbx, rbx
0x1800521db  jz      short loc_1800521F1
0x1800521dd  call    cs:__imp_GetProcessHeap
0x1800521e3  mov     r8, rbx; lpMem
0x1800521e6  xor     edx, edx; dwFlags
0x1800521e8  mov     rcx, rax; hHeap
0x1800521eb  call    cs:__imp_HeapFree
0x1800521f1  xor     ebx, ebx
0x1800521f3  mov     rcx, rsi; this
0x1800521f6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800521fb  mov     eax, ebx
0x1800521fd  add     rsp, 68h
0x180052201  pop     r15
0x180052203  pop     r14
0x180052205  pop     rdi
0x180052206  pop     rsi
0x180052207  pop     rbx
0x180052208  pop     rbp
0x180052209  retn
```
