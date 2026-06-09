# AddUserToHandle(void *,void *,ulong)

- ea: `0x1800957e0`
- end: `0x1800959de`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180068c84`

## callees

- `0x180010c04`
- `0x180034b2c`
- `0x1800957e0`
- `0x1800959e4`
- `0x18009e664`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009599e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800959bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009599e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800959bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009584b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009593b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095990`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800959b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009584b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009593b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095990`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800959b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095859`
- `ntdll!NtQuerySecurityObject` at `0x180095813`
- `ntdll!NtQuerySecurityObject` at `0x18009589f`
- `ntdll!NtQuerySecurityObject` at `0x180095813`
- `ntdll!NtQuerySecurityObject` at `0x18009589f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800958c8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800958c8`
- `ntdll!NtSetSecurityObject` at `0x180095963`
- `ntdll!NtSetSecurityObject` at `0x180095963`

## string_xrefs

- `0x180095828`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18009586b`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800958db`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18009591a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180095971`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall AddUserToHandle(HANDLE Handle, void *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  ULONG v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  int v11; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdi
  HANDLE v17; // rax
  NTSTATUS v18; // eax
  int v19; // eax
  void *v20; // rbx
  int v21; // edi
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
0x1800957e0  push    rbp
0x1800957e2  push    rbx
0x1800957e3  push    rsi
0x1800957e4  push    rdi
0x1800957e5  push    r14
0x1800957e7  push    r15
0x1800957e9  mov     rbp, rsp
0x1800957ec  sub     rsp, 68h
0x1800957f0  xor     r9d, r9d; Length
0x1800957f3  mov     [rbp+Length], 0
0x1800957fa  mov     r14d, r8d
0x1800957fd  lea     rax, [rbp+Length]
0x180095801  mov     r15, rdx
0x180095804  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180095809  xor     r8d, r8d; SecurityDescriptor
0x18009580c  mov     rdi, rcx
0x18009580f  lea     edx, [r9+4]; SecurityInformation
0x180095813  call    cs:__imp_NtQuerySecurityObject
0x180095819  cmp     eax, 0C0000023h
0x18009581e  jz      short loc_180095848
0x180095820  test    eax, eax
0x180095822  jns     short loc_180095841
0x180095824  mov     rcx, [rbp+30h]; this
0x180095828  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18009582f  mov     r9d, eax; char *
0x180095832  mov     edx, 62h ; 'b'; void *
0x180095837  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18009583c  jmp     loc_1800959D1
0x180095841  xor     eax, eax
0x180095843  jmp     loc_1800959D1
0x180095848  mov     ebx, [rbp+Length]
0x18009584b  call    cs:__imp_GetProcessHeap
0x180095851  mov     r8d, ebx; dwBytes
0x180095854  xor     edx, edx; dwFlags
0x180095856  mov     rcx, rax; hHeap
0x180095859  call    cs:__imp_HeapAlloc
0x18009585f  mov     rsi, rax
0x180095862  test    rax, rax
0x180095865  jnz     short loc_180095887
0x180095867  mov     rcx, [rbp+30h]; this
0x18009586b  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095872  mov     ebx, 8007000Eh
0x180095877  lea     edx, [rax+66h]; void *
0x18009587a  mov     r9d, ebx; char *
0x18009587d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095882  jmp     loc_1800959CF
0x180095887  mov     r9d, [rbp+Length]; Length
0x18009588b  lea     rax, [rbp+Length]
0x18009588f  mov     r8, rsi; SecurityDescriptor
0x180095892  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180095897  mov     edx, 4; SecurityInformation
0x18009589c  mov     rcx, rdi; Handle
0x18009589f  call    cs:__imp_NtQuerySecurityObject
0x1800958a5  test    eax, eax
0x1800958a7  jns     short loc_1800958B0
0x1800958a9  mov     edx, 69h ; 'i'
0x1800958ae  jmp     short loc_1800958D7
0x1800958b0  xor     eax, eax
0x1800958b2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800958b6  xorps   xmm0, xmm0
0x1800958b9  mov     [rbp+lpMem], rax
0x1800958bd  movups  [rbp+SecurityDescriptor], xmm0
0x1800958c1  lea     edx, [rax+1]; Revision
0x1800958c4  movups  [rbp+var_20], xmm0
0x1800958c8  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800958ce  test    eax, eax
0x1800958d0  jns     short loc_1800958F1
0x1800958d2  mov     edx, 6Ch ; 'l'; void *
0x1800958d7  mov     rcx, [rbp+30h]; this
0x1800958db  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800958e2  mov     r9d, eax; char *
0x1800958e5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800958ea  mov     ebx, eax
0x1800958ec  jmp     loc_1800959C7
0x1800958f1  lea     rax, [rbp+SecurityDescriptor]
0x1800958f5  mov     [rbp+arg_18], 0
0x1800958f9  lea     r9, [rbp+arg_18]; bool *
0x1800958fd  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x180095902  mov     r8d, r14d; unsigned int
0x180095905  mov     rdx, r15; void *
0x180095908  mov     rcx, rsi; void *
0x18009590b  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x180095910  mov     ebx, eax
0x180095912  test    eax, eax
0x180095914  jns     short loc_180095951
0x180095916  mov     rcx, [rbp+30h]; this
0x18009591a  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095921  mov     r9d, eax; char *
0x180095924  mov     edx, 72h ; 'r'; void *
0x180095929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009592e  mov     rdi, [rbp+lpMem]
0x180095932  test    rdi, rdi
0x180095935  jz      loc_1800959C7
0x18009593b  call    cs:__imp_GetProcessHeap
0x180095941  mov     r8, rdi; lpMem
0x180095944  xor     edx, edx; dwFlags
0x180095946  mov     rcx, rax; hHeap
0x180095949  call    cs:__imp_HeapFree
0x18009594f  jmp     short loc_1800959C7
0x180095951  cmp     [rbp+arg_18], 0
0x180095955  jnz     short loc_1800959A8
0x180095957  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18009595b  mov     edx, 4; SecurityInformation
0x180095960  mov     rcx, rdi; Handle
0x180095963  call    cs:__imp_NtSetSecurityObject
0x180095969  test    eax, eax
0x18009596b  jns     short loc_1800959A8
0x18009596d  mov     rcx, [rbp+30h]; this
0x180095971  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095978  mov     r9d, eax; char *
0x18009597b  mov     edx, 79h ; 'y'; void *
0x180095980  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180095985  mov     rbx, [rbp+lpMem]
0x180095989  mov     edi, eax
0x18009598b  test    rbx, rbx
0x18009598e  jz      short loc_1800959A4
0x180095990  call    cs:__imp_GetProcessHeap
0x180095996  mov     r8, rbx; lpMem
0x180095999  xor     edx, edx; dwFlags
0x18009599b  mov     rcx, rax; hHeap
0x18009599e  call    cs:__imp_HeapFree
0x1800959a4  mov     ebx, edi
0x1800959a6  jmp     short loc_1800959C7
0x1800959a8  mov     rbx, [rbp+lpMem]
0x1800959ac  test    rbx, rbx
0x1800959af  jz      short loc_1800959C5
0x1800959b1  call    cs:__imp_GetProcessHeap
0x1800959b7  mov     r8, rbx; lpMem
0x1800959ba  xor     edx, edx; dwFlags
0x1800959bc  mov     rcx, rax; hHeap
0x1800959bf  call    cs:__imp_HeapFree
0x1800959c5  xor     ebx, ebx
0x1800959c7  mov     rcx, rsi; this
0x1800959ca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800959cf  mov     eax, ebx
0x1800959d1  add     rsp, 68h
0x1800959d5  pop     r15
0x1800959d7  pop     r14
0x1800959d9  pop     rdi
0x1800959da  pop     rsi
0x1800959db  pop     rbx
0x1800959dc  pop     rbp
0x1800959dd  retn
```
