# InitializeSecurity

- ea: `0x140007ebc`
- end: `0x14000811b`
- name: `InitializeSecurity`
- size: `607`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006080`

## callees

- `0x140007990`
- `0x140007b28`
- `0x140007ebc`
- `0x140009010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400080e6`
- `ntdll!RtlFreeHeap` at `0x140008103`
- `ntdll!RtlFreeHeap` at `0x1400080e6`
- `ntdll!RtlFreeHeap` at `0x140008103`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007f87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007f87`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140008022`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140008022`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007f5b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007f5b`

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
0x140007ebc  push    rbp
0x140007ebe  push    rbx
0x140007ebf  push    rsi
0x140007ec0  push    rdi
0x140007ec1  push    r15
0x140007ec3  mov     rbp, rsp
0x140007ec6  sub     rsp, 50h
0x140007eca  mov     r9d, [rcx+94h]
0x140007ed1  mov     rdi, rcx
0x140007ed4  mov     r15d, 1
0x140007eda  mov     [rbp+pSecDesc], 0
0x140007ee2  mov     ecx, r9d
0x140007ee5  mov     edx, r9d
0x140007ee8  mov     r8d, r9d
0x140007eeb  shr     ecx, 1
0x140007eed  mov     rax, [rdi+98h]
0x140007ef4  xor     esi, esi
0x140007ef6  shr     edx, 4
0x140007ef9  and     ecx, r15d; int
0x140007efc  shr     r8d, 5
0x140007f00  and     edx, r15d; int
0x140007f03  shr     r9d, 6
0x140007f07  and     r8d, r15d; int
0x140007f0a  and     r9d, r15d; int
0x140007f0d  mov     [rbp+P], rsi
0x140007f11  mov     [rbp+arg_0], rsi
0x140007f15  test    rax, rax
0x140007f18  jnz     short loc_140007F46
0x140007f1a  lea     rax, [rbp+P]
0x140007f1e  mov     qword ptr [rsp+50h+dwImpLevel], rax; struct _ACL **
0x140007f23  lea     rax, [rbp+pSecDesc]
0x140007f27  mov     [rsp+50h+ppv], rax; void **
0x140007f2c  call    ?InitializeSdFromProcessToken@@YAKHHHHPEAPEAXPEAPEAU_ACL@@@Z; InitializeSdFromProcessToken(int,int,int,int,void * *,_ACL * *)
0x140007f31  mov     rsi, [rbp+P]
0x140007f35  test    eax, eax
0x140007f37  jz      short loc_140007F54
0x140007f39  mov     ebx, 80070000h
0x140007f3e  cmovle  ebx, eax
0x140007f41  jmp     loc_1400080B9
0x140007f46  lea     rdx, [rbp+pSecDesc]; void **
0x140007f4a  mov     rcx, rax; pSelfRelativeSecurityDescriptor
0x140007f4d  call    ?GetAbsoluteSd@@YAKPEAXPEAPEAX@Z; GetAbsoluteSd(void *,void * *)
0x140007f52  jmp     short loc_140007F35
0x140007f54  mov     edx, 4; dwCoInit
0x140007f59  xor     ecx, ecx; pvReserved
0x140007f5b  call    cs:__imp_CoInitializeEx
0x140007f61  mov     ebx, eax
0x140007f63  test    eax, eax
0x140007f65  js      loc_1400080B9
0x140007f6b  lea     rax, [rbp+arg_0]
0x140007f6f  mov     r8d, r15d; dwClsContext
0x140007f72  lea     r9, IID_IGlobalOptions; riid
0x140007f79  mov     [rsp+50h+ppv], rax; ppv
0x140007f7e  xor     edx, edx; pUnkOuter
0x140007f80  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007f87  call    cs:__imp_CoCreateInstance
0x140007f8d  mov     ebx, eax
0x140007f8f  test    eax, eax
0x140007f91  js      loc_1400080B9
0x140007f97  cmp     dword ptr [rdi+4Ch], 0FFFFh
0x140007f9e  jz      short loc_140007FC3
0x140007fa0  mov     rcx, [rbp+arg_0]
0x140007fa4  mov     edx, 4
0x140007fa9  mov     r8d, [rdi+4Ch]
0x140007fad  mov     rax, [rcx]
0x140007fb0  mov     rax, [rax+18h]
0x140007fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fb9  mov     ebx, eax
0x140007fbb  test    eax, eax
0x140007fbd  js      loc_1400080B9
0x140007fc3  cmp     cs:ServiceCount, r15d
0x140007fca  jbe     short loc_140007FEE
0x140007fcc  mov     rcx, [rbp+arg_0]
0x140007fd0  mov     r8, r15
0x140007fd3  mov     edx, 8
0x140007fd8  mov     rax, [rcx]
0x140007fdb  mov     rax, [rax+18h]
0x140007fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fe4  mov     ebx, eax
0x140007fe6  test    eax, eax
0x140007fe8  js      loc_1400080B9
0x140007fee  mov     eax, [rdi+34h]
0x140007ff1  xor     r9d, r9d; pReserved1
0x140007ff4  mov     rcx, [rbp+pSecDesc]; pSecDesc
0x140007ff8  xor     r8d, r8d; asAuthSvc
0x140007ffb  mov     [rsp+50h+pReserved3], 0; pReserved3
0x140008004  or      edx, 0FFFFFFFFh; cAuthSvc
0x140008007  mov     [rsp+50h+dwCapabilities], eax; dwCapabilities
0x14000800b  mov     eax, [rdi+30h]
0x14000800e  mov     [rsp+50h+pAuthList], 0; pAuthList
0x140008017  mov     [rsp+50h+dwImpLevel], eax; dwImpLevel
0x14000801b  mov     eax, [rdi+2Ch]
0x14000801e  mov     dword ptr [rsp+50h+ppv], eax; dwAuthnLevel
0x140008022  call    cs:__imp_CoInitializeSecurity
0x140008028  mov     ebx, eax
0x14000802a  test    eax, eax
0x14000802c  js      loc_1400080B9
0x140008032  mov     rcx, [rbp+arg_0]
0x140008036  mov     r8d, 2
0x14000803c  mov     edx, r15d
0x14000803f  mov     rax, [rcx]
0x140008042  mov     rax, [rax+18h]
0x140008046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000804b  mov     ebx, eax
0x14000804d  test    eax, eax
0x14000804f  js      short loc_1400080B9
0x140008051  cmp     dword ptr [rdi+48h], 0FFFFh
0x140008058  jz      short loc_140008079
0x14000805a  mov     rcx, [rbp+arg_0]
0x14000805e  mov     edx, 5
0x140008063  mov     r8d, [rdi+48h]
0x140008067  mov     rax, [rcx]
0x14000806a  mov     rax, [rax+18h]
0x14000806e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008073  mov     ebx, eax
0x140008075  test    eax, eax
0x140008077  js      short loc_1400080B9
0x140008079  cmp     cs:ServiceCount, r15d
0x140008080  jnz     short loc_1400080B9
0x140008082  lea     r8, [rdi+38h]
0x140008086  mov     rax, [r8]
0x140008089  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140008090  jnz     short loc_14000809D
0x140008092  mov     rax, [r8+8]
0x140008096  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14000809d  test    rax, rax
0x1400080a0  jz      short loc_1400080B9
0x1400080a2  mov     rcx, [rbp+arg_0]
0x1400080a6  mov     edx, 2
0x1400080ab  mov     rax, [rcx]
0x1400080ae  mov     rax, [rax+18h]
0x1400080b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080b7  mov     ebx, eax
0x1400080b9  mov     rcx, [rbp+arg_0]
0x1400080bd  test    rcx, rcx
0x1400080c0  jz      short loc_1400080CE
0x1400080c2  mov     rax, [rcx]
0x1400080c5  mov     rax, [rax+10h]
0x1400080c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080ce  mov     r8, [rbp+pSecDesc]; P
0x1400080d2  test    r8, r8
0x1400080d5  jz      short loc_1400080EC
0x1400080d7  mov     rcx, gs:60h
0x1400080e0  xor     edx, edx; Flags
0x1400080e2  mov     rcx, [rcx+30h]; HeapHandle
0x1400080e6  call    cs:__imp_RtlFreeHeap
0x1400080ec  test    rsi, rsi
0x1400080ef  jz      short loc_140008109
0x1400080f1  mov     rcx, gs:60h
0x1400080fa  mov     r8, rsi; P
0x1400080fd  xor     edx, edx; Flags
0x1400080ff  mov     rcx, [rcx+30h]; HeapHandle
0x140008103  call    cs:__imp_RtlFreeHeap
0x140008109  not     ebx
0x14000810b  shr     ebx, 1Fh
0x14000810e  mov     eax, ebx
0x140008110  add     rsp, 50h
0x140008114  pop     r15
0x140008116  pop     rdi
0x140008117  pop     rsi
0x140008118  pop     rbx
0x140008119  pop     rbp
0x14000811a  retn
```
