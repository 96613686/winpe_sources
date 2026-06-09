# InitializeSecurity

- ea: `0x140008474`
- end: `0x1400086f2`
- name: `InitializeSecurity`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006520`

## callees

- `0x140007e80`
- `0x140008040`
- `0x140008474`
- `0x140009010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400086b0`
- `ntdll!RtlFreeHeap` at `0x1400086d3`
- `ntdll!RtlFreeHeap` at `0x1400086b0`
- `ntdll!RtlFreeHeap` at `0x1400086d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008545`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008545`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400085e6`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400085e6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140008513`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140008513`

## pseudocode

```c
_BOOL8 __fastcall InitializeSecurity(__int64 a1)
{
  unsigned int v1; // r9d
  void *v3; // rax
  PVOID v4; // rsi
  int v5; // ecx
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int AbsoluteSd; // eax
  HRESULT v10; // ebx
  __int64 v11; // rax
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc; // [rsp+88h] [rbp+38h] BYREF
  PVOID P; // [rsp+90h] [rbp+40h] BYREF

  v1 = *(_DWORD *)(a1 + 148);
  pSecDesc = 0;
  v3 = *(void **)(a1 + 152);
  v4 = 0;
  v5 = (v1 >> 1) & 1;
  v6 = (v1 >> 4) & 1;
  v7 = (v1 >> 5) & 1;
  v8 = (v1 >> 6) & 1;
  P = 0;
  ppv = 0;
  if ( v3 )
  {
    AbsoluteSd = GetAbsoluteSd(v3, &pSecDesc);
  }
  else
  {
    AbsoluteSd = InitializeSdFromProcessToken(v5, v6, v7, v8, &pSecDesc, (struct _ACL **)&P);
    v4 = P;
  }
  if ( AbsoluteSd )
  {
    v10 = -2147024896;
    if ( AbsoluteSd <= 0 )
      v10 = AbsoluteSd;
  }
  else
  {
    v10 = CoInitializeEx(0, 4u);
    if ( v10 >= 0 )
    {
      v10 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
      if ( v10 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 76) == 0xFFFF
          || (v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      4,
                      *(unsigned int *)(a1 + 76)),
              v10 >= 0) )
        {
          if ( (unsigned int)ServiceCount <= 1
            || (v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 8, 1), v10 >= 0) )
          {
            v10 = CoInitializeSecurity(
                    pSecDesc,
                    -1,
                    0,
                    0,
                    *(_DWORD *)(a1 + 44),
                    *(_DWORD *)(a1 + 48),
                    0,
                    *(_DWORD *)(a1 + 52),
                    0);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
              if ( v10 >= 0 )
              {
                if ( *(_DWORD *)(a1 + 72) == 0xFFFF
                  || (v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 24LL))(
                              ppv,
                              5,
                              *(unsigned int *)(a1 + 72)),
                      v10 >= 0) )
                {
                  if ( ServiceCount == 1 )
                  {
                    v11 = *(_QWORD *)(a1 + 56) - *(_QWORD *)&GUID_NULL.Data1;
                    if ( !v11 )
                      v11 = *(_QWORD *)(a1 + 64) - *(_QWORD *)GUID_NULL.Data4;
                    if ( v11 )
                      v10 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 2);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( pSecDesc )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pSecDesc);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v10 >= 0;
}

```

## disassembly

```asm
0x140008474  push    rbp
0x140008476  push    rbx
0x140008477  push    rsi
0x140008478  push    rdi
0x140008479  push    r15
0x14000847b  mov     rbp, rsp
0x14000847e  sub     rsp, 50h
0x140008482  mov     r9d, [rcx+94h]
0x140008489  mov     rdi, rcx
0x14000848c  mov     r15d, 1
0x140008492  mov     [rbp+pSecDesc], 0
0x14000849a  mov     ecx, r9d
0x14000849d  mov     edx, r9d
0x1400084a0  mov     r8d, r9d
0x1400084a3  shr     ecx, 1
0x1400084a5  mov     rax, [rdi+98h]
0x1400084ac  xor     esi, esi
0x1400084ae  shr     edx, 4
0x1400084b1  and     ecx, r15d; int
0x1400084b4  shr     r8d, 5
0x1400084b8  and     edx, r15d; int
0x1400084bb  shr     r9d, 6
0x1400084bf  and     r8d, r15d; int
0x1400084c2  and     r9d, r15d; int
0x1400084c5  mov     [rbp+P], rsi
0x1400084c9  mov     [rbp+arg_0], rsi
0x1400084cd  test    rax, rax
0x1400084d0  jnz     short loc_1400084FE
0x1400084d2  lea     rax, [rbp+P]
0x1400084d6  mov     qword ptr [rsp+50h+dwImpLevel], rax; struct _ACL **
0x1400084db  lea     rax, [rbp+pSecDesc]
0x1400084df  mov     [rsp+50h+ppv], rax; void **
0x1400084e4  call    ?InitializeSdFromProcessToken@@YAKHHHHPEAPEAXPEAPEAU_ACL@@@Z; InitializeSdFromProcessToken(int,int,int,int,void * *,_ACL * *)
0x1400084e9  mov     rsi, [rbp+P]
0x1400084ed  test    eax, eax
0x1400084ef  jz      short loc_14000850C
0x1400084f1  mov     ebx, 80070000h
0x1400084f6  cmovle  ebx, eax
0x1400084f9  jmp     loc_140008683
0x1400084fe  lea     rdx, [rbp+pSecDesc]; void **
0x140008502  mov     rcx, rax; pSelfRelativeSecurityDescriptor
0x140008505  call    ?GetAbsoluteSd@@YAKPEAXPEAPEAX@Z; GetAbsoluteSd(void *,void * *)
0x14000850a  jmp     short loc_1400084ED
0x14000850c  mov     edx, 4; dwCoInit
0x140008511  xor     ecx, ecx; pvReserved
0x140008513  call    cs:__imp_CoInitializeEx
0x14000851a  nop     dword ptr [rax+rax+00h]
0x14000851f  mov     ebx, eax
0x140008521  test    eax, eax
0x140008523  js      loc_140008683
0x140008529  lea     rax, [rbp+arg_0]
0x14000852d  mov     r8d, r15d; dwClsContext
0x140008530  lea     r9, IID_IGlobalOptions; riid
0x140008537  mov     [rsp+50h+ppv], rax; ppv
0x14000853c  xor     edx, edx; pUnkOuter
0x14000853e  lea     rcx, CLSID_GlobalOptions; rclsid
0x140008545  call    cs:__imp_CoCreateInstance
0x14000854c  nop     dword ptr [rax+rax+00h]
0x140008551  mov     ebx, eax
0x140008553  test    eax, eax
0x140008555  js      loc_140008683
0x14000855b  cmp     dword ptr [rdi+4Ch], 0FFFFh
0x140008562  jz      short loc_140008587
0x140008564  mov     rcx, [rbp+arg_0]
0x140008568  mov     edx, 4
0x14000856d  mov     r8d, [rdi+4Ch]
0x140008571  mov     rax, [rcx]
0x140008574  mov     rax, [rax+18h]
0x140008578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000857d  mov     ebx, eax
0x14000857f  test    eax, eax
0x140008581  js      loc_140008683
0x140008587  cmp     cs:ServiceCount, r15d
0x14000858e  jbe     short loc_1400085B2
0x140008590  mov     rcx, [rbp+arg_0]
0x140008594  mov     r8, r15
0x140008597  mov     edx, 8
0x14000859c  mov     rax, [rcx]
0x14000859f  mov     rax, [rax+18h]
0x1400085a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085a8  mov     ebx, eax
0x1400085aa  test    eax, eax
0x1400085ac  js      loc_140008683
0x1400085b2  mov     eax, [rdi+34h]
0x1400085b5  xor     r9d, r9d; pReserved1
0x1400085b8  mov     rcx, [rbp+pSecDesc]; pSecDesc
0x1400085bc  xor     r8d, r8d; asAuthSvc
0x1400085bf  mov     [rsp+50h+pReserved3], 0; pReserved3
0x1400085c8  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400085cb  mov     [rsp+50h+dwCapabilities], eax; dwCapabilities
0x1400085cf  mov     eax, [rdi+30h]
0x1400085d2  mov     [rsp+50h+pAuthList], 0; pAuthList
0x1400085db  mov     [rsp+50h+dwImpLevel], eax; dwImpLevel
0x1400085df  mov     eax, [rdi+2Ch]
0x1400085e2  mov     dword ptr [rsp+50h+ppv], eax; dwAuthnLevel
0x1400085e6  call    cs:__imp_CoInitializeSecurity
0x1400085ed  nop     dword ptr [rax+rax+00h]
0x1400085f2  mov     ebx, eax
0x1400085f4  test    eax, eax
0x1400085f6  js      loc_140008683
0x1400085fc  mov     rcx, [rbp+arg_0]
0x140008600  mov     r8d, 2
0x140008606  mov     edx, r15d
0x140008609  mov     rax, [rcx]
0x14000860c  mov     rax, [rax+18h]
0x140008610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008615  mov     ebx, eax
0x140008617  test    eax, eax
0x140008619  js      short loc_140008683
0x14000861b  cmp     dword ptr [rdi+48h], 0FFFFh
0x140008622  jz      short loc_140008643
0x140008624  mov     rcx, [rbp+arg_0]
0x140008628  mov     edx, 5
0x14000862d  mov     r8d, [rdi+48h]
0x140008631  mov     rax, [rcx]
0x140008634  mov     rax, [rax+18h]
0x140008638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000863d  mov     ebx, eax
0x14000863f  test    eax, eax
0x140008641  js      short loc_140008683
0x140008643  cmp     cs:ServiceCount, r15d
0x14000864a  jnz     short loc_140008683
0x14000864c  lea     r8, [rdi+38h]
0x140008650  mov     rax, [r8]
0x140008653  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14000865a  jnz     short loc_140008667
0x14000865c  mov     rax, [r8+8]
0x140008660  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140008667  test    rax, rax
0x14000866a  jz      short loc_140008683
0x14000866c  mov     rcx, [rbp+arg_0]
0x140008670  mov     edx, 2
0x140008675  mov     rax, [rcx]
0x140008678  mov     rax, [rax+18h]
0x14000867c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008681  mov     ebx, eax
0x140008683  mov     rcx, [rbp+arg_0]
0x140008687  test    rcx, rcx
0x14000868a  jz      short loc_140008698
0x14000868c  mov     rax, [rcx]
0x14000868f  mov     rax, [rax+10h]
0x140008693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008698  mov     r8, [rbp+pSecDesc]; P
0x14000869c  test    r8, r8
0x14000869f  jz      short loc_1400086BC
0x1400086a1  mov     rcx, gs:60h
0x1400086aa  xor     edx, edx; Flags
0x1400086ac  mov     rcx, [rcx+30h]; HeapHandle
0x1400086b0  call    cs:__imp_RtlFreeHeap
0x1400086b7  nop     dword ptr [rax+rax+00h]
0x1400086bc  test    rsi, rsi
0x1400086bf  jz      short loc_1400086DF
0x1400086c1  mov     rcx, gs:60h
0x1400086ca  mov     r8, rsi; P
0x1400086cd  xor     edx, edx; Flags
0x1400086cf  mov     rcx, [rcx+30h]; HeapHandle
0x1400086d3  call    cs:__imp_RtlFreeHeap
0x1400086da  nop     dword ptr [rax+rax+00h]
0x1400086df  not     ebx
0x1400086e1  shr     ebx, 1Fh
0x1400086e4  mov     eax, ebx
0x1400086e6  add     rsp, 50h
0x1400086ea  pop     r15
0x1400086ec  pop     rdi
0x1400086ed  pop     rsi
0x1400086ee  pop     rbx
0x1400086ef  pop     rbp
0x1400086f0  retn
```
