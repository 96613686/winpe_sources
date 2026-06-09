# CoCreateElevatedInstance(HWND__ *,IMultiObjectElevationFactory * *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000f024`
- end: `0x18000f0fc`
- name: `?CoCreateElevatedInstance@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@AEBU_GUID@@2PEAPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(HWND, LPVOID *ppv, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bd98`
- `0x18000beb8`
- `0x18000bf70`
- `0x18002ea84`
- `0x18002f9c8`

## callees

- `0x18000ae04`
- `0x18000f024`
- `0x18000f104`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f05f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f05f`

## pseudocode

```c
__int64 __fastcall CoCreateElevatedInstance(
        HWND a1,
        LPVOID *ppv,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT Instance; // ebx
  HRESULT InstanceAsAdmin; // eax

  if ( !ppv )
  {
    InstanceAsAdmin = CoCreateInstanceAsAdmin(a1, a3, a4, a5);
    goto LABEL_7;
  }
  if ( *ppv
    || (Instance = CoCreateInstance(
                     &CLSID_MultiObjectElevationFactory,
                     0,
                     1u,
                     &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e,
                     ppv),
        Instance >= 0)
    && (Instance = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)*ppv + 24LL))(
                     *ppv,
                     a1,
                     qword_18003C8A8),
        Instance >= 0) )
  {
    InstanceAsAdmin = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)*ppv + 40LL))(
                        *ppv,
                        a3,
                        a4,
                        a5);
LABEL_7:
    Instance = InstanceAsAdmin;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f024  push    rbx
0x18000f026  push    rbp
0x18000f027  push    rsi
0x18000f028  push    rdi
0x18000f029  push    r14
0x18000f02b  sub     rsp, 30h
0x18000f02f  mov     rbp, r9
0x18000f032  mov     r14, r8
0x18000f035  mov     rdi, rdx
0x18000f038  mov     rsi, rcx
0x18000f03b  test    rdx, rdx
0x18000f03e  jz      short loc_18000F0A9
0x18000f040  cmp     qword ptr [rdx], 0
0x18000f044  jnz     short loc_18000F08A
0x18000f046  mov     [rsp+58h+ppv], rdx; ppv
0x18000f04b  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x18000f052  xor     edx, edx; pUnkOuter
0x18000f054  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x18000f05b  lea     r8d, [rdx+1]; dwClsContext
0x18000f05f  call    cs:__imp_CoCreateInstance
0x18000f065  mov     ebx, eax
0x18000f067  test    eax, eax
0x18000f069  js      short loc_18000F0BE
0x18000f06b  mov     rcx, [rdi]
0x18000f06e  lea     r8, qword_18003C8A8
0x18000f075  mov     rdx, rsi
0x18000f078  mov     rax, [rcx]
0x18000f07b  mov     rax, [rax+18h]
0x18000f07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f084  mov     ebx, eax
0x18000f086  test    eax, eax
0x18000f088  js      short loc_18000F0BE
0x18000f08a  mov     rcx, [rdi]
0x18000f08d  mov     r8, rbp
0x18000f090  mov     r9, [rsp+58h+arg_20]
0x18000f098  mov     rdx, r14
0x18000f09b  mov     rax, [rcx]
0x18000f09e  mov     rax, [rax+28h]
0x18000f0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a7  jmp     short loc_18000F0BC
0x18000f0a9  mov     r9, [rsp+58h+arg_20]; void **
0x18000f0b1  mov     r8, rbp; struct _GUID *
0x18000f0b4  mov     rdx, r14; struct _GUID *
0x18000f0b7  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000f0bc  mov     ebx, eax
0x18000f0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0c5  lea     rax, WPP_GLOBAL_Control
0x18000f0cc  cmp     rcx, rax
0x18000f0cf  jz      short loc_18000F0EF
0x18000f0d1  test    byte ptr [rcx+1Ch], 10h
0x18000f0d5  jz      short loc_18000F0EF
0x18000f0d7  mov     rcx, [rcx+10h]
0x18000f0db  lea     r8, WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids
0x18000f0e2  mov     edx, 0Ch
0x18000f0e7  mov     r9d, ebx
0x18000f0ea  call    WPP_SF_d
0x18000f0ef  mov     eax, ebx
0x18000f0f1  add     rsp, 30h
0x18000f0f5  pop     r14
0x18000f0f7  pop     rdi
0x18000f0f8  pop     rsi
0x18000f0f9  pop     rbp
0x18000f0fa  pop     rbx
0x18000f0fb  retn
```
