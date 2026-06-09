# IsNetworkConnected(int *)

- ea: `0x18000ae94`
- end: `0x18000afa0`
- name: `?IsNetworkConnected@@YAJPEAH@Z`
- size: `268`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c3d0`
- `0x180012a10`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000ae94`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000af17`
- `ole32!CoCreateInstance` at `0x18000af17`

## pseudocode

```c
__int64 __fastcall IsNetworkConnected(int *a1)
{
  _QWORD *v2; // rcx
  HRESULT v3; // ebx
  __int16 v5; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    *a1 = 0;
    ppv = 0;
    v3 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
    if ( v3 >= 0 )
    {
      v5 = 0;
      v3 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 96LL))(ppv, &v5);
      if ( v3 >= 0 )
        *a1 = v5 == -1;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    v2 = WPP_GLOBAL_Control;
  }
  else
  {
    v3 = -2147467261;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 268, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ae94  mov     [rsp+arg_10], rbx
0x18000ae99  mov     [rsp+arg_18], rsi
0x18000ae9e  push    rdi
0x18000ae9f  sub     rsp, 30h
0x18000aea3  mov     rdi, rcx
0x18000aea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aead  lea     rsi, WPP_GLOBAL_Control
0x18000aeb4  cmp     rcx, rsi
0x18000aeb7  jz      short loc_18000AEDB
0x18000aeb9  test    byte ptr [rcx+1Ch], 20h
0x18000aebd  jz      short loc_18000AEDB
0x18000aebf  mov     rcx, [rcx+10h]
0x18000aec3  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000aeca  mov     edx, 10Bh
0x18000aecf  call    WPP_SF_
0x18000aed4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aedb  test    rdi, rdi
0x18000aede  jnz     short loc_18000AEEA
0x18000aee0  mov     ebx, 80004003h
0x18000aee5  jmp     loc_18000AF6B
0x18000aeea  xor     edx, edx; pUnkOuter
0x18000aeec  mov     dword ptr [rdi], 0
0x18000aef2  lea     rax, [rsp+38h+arg_8]
0x18000aef7  mov     [rsp+38h+arg_8], 0
0x18000af00  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18000af07  mov     [rsp+38h+ppv], rax; ppv
0x18000af0c  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000af13  lea     r8d, [rdx+1]; dwClsContext
0x18000af17  call    cs:__imp_CoCreateInstance
0x18000af1d  mov     ebx, eax
0x18000af1f  test    eax, eax
0x18000af21  js      short loc_18000AF64
0x18000af23  mov     rcx, [rsp+38h+arg_8]
0x18000af28  lea     rdx, [rsp+38h+arg_0]
0x18000af2d  xor     eax, eax
0x18000af2f  mov     [rsp+38h+arg_0], ax
0x18000af34  mov     rax, [rcx]
0x18000af37  mov     rax, [rax+60h]
0x18000af3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af40  mov     ebx, eax
0x18000af42  test    eax, eax
0x18000af44  js      short loc_18000AF53
0x18000af46  xor     eax, eax
0x18000af48  cmp     [rsp+38h+arg_0], 0FFFFh
0x18000af4e  setz    al
0x18000af51  mov     [rdi], eax
0x18000af53  mov     rcx, [rsp+38h+arg_8]
0x18000af58  mov     rax, [rcx]
0x18000af5b  mov     rax, [rax+10h]
0x18000af5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af6b  cmp     rcx, rsi
0x18000af6e  jz      short loc_18000AF8E
0x18000af70  test    byte ptr [rcx+1Ch], 20h
0x18000af74  jz      short loc_18000AF8E
0x18000af76  mov     rcx, [rcx+10h]
0x18000af7a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000af81  mov     edx, 10Ch
0x18000af86  mov     r9d, ebx
0x18000af89  call    WPP_SF_d
0x18000af8e  mov     rsi, [rsp+38h+arg_18]
0x18000af93  mov     eax, ebx
0x18000af95  mov     rbx, [rsp+38h+arg_10]
0x18000af9a  add     rsp, 30h
0x18000af9e  pop     rdi
0x18000af9f  retn
```
