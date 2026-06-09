# UtilIsNetworkConnected(void)

- ea: `0x14001ad44`
- end: `0x14001aebb`
- name: `?UtilIsNetworkConnected@@YAHXZ`
- size: `375`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005f98`

## callees

- `0x14000e340`
- `0x14001ad44`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001ad62`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001ad62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001aded`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001aded`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001aea8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001aea8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 UtilIsNetworkConnected(void)
{
  BOOL v0; // edi
  HRESULT v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r9
  HRESULT v5; // esi
  LPVOID v6; // rcx
  int v7; // eax
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID *v10; // [rsp+38h] [rbp-18h]
  __int16 v11; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v12; // [rsp+88h] [rbp+38h]
  __int64 v13; // [rsp+90h] [rbp+40h] BYREF

  v11 = 0;
  v0 = 1;
  v1 = CoInitializeEx(0, 0);
  v12 = v1;
  v13 = 0;
  if ( (int)(v1 + 0x80000000) < 0 || v1 == -2147417850 )
  {
    ppv = 0;
    v10 = (LPVOID *)&v13;
    v13 = 0;
    v5 = CoCreateInstance(
           &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
           0,
           0x17u,
           &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
           &ppv);
    if ( ppv )
    {
      v6 = *v10;
      *v10 = ppv;
      if ( v6 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    if ( v5 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v13 + 96LL))(v13, &v11);
      v4 = (unsigned int)v7;
      if ( v7 >= 0 )
      {
        v0 = v11 != 0;
      }
      else
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v3 = 27;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 26;
        v4 = (unsigned int)v5;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 25;
      v4 = (unsigned int)v1;
LABEL_6:
      WPP_SF_d(v2[2], v3, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v4);
    }
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v1 >= 0 )
    CoUninitialize();
  return v0;
}

```

## disassembly

```asm
0x14001ad44  push    rbp
0x14001ad46  push    rbx
0x14001ad47  push    rsi
0x14001ad48  push    rdi
0x14001ad49  push    r14
0x14001ad4b  mov     rbp, rsp
0x14001ad4e  sub     rsp, 50h
0x14001ad52  xor     r14d, r14d
0x14001ad55  mov     [rbp+arg_0], r14w
0x14001ad5a  lea     edi, [r14+1]
0x14001ad5e  xor     edx, edx; dwCoInit
0x14001ad60  xor     ecx, ecx; pvReserved
0x14001ad62  call    cs:__imp_CoInitializeEx
0x14001ad68  mov     ebx, eax
0x14001ad6a  mov     [rbp+arg_8], eax
0x14001ad6d  mov     [rbp+arg_10], r14
0x14001ad71  mov     ecx, 80000000h
0x14001ad76  add     eax, ecx
0x14001ad78  test    ecx, eax
0x14001ad7a  jnz     short loc_14001ADC0
0x14001ad7c  cmp     ebx, 80010106h
0x14001ad82  jz      short loc_14001ADC0
0x14001ad84  lea     rax, WPP_GLOBAL_Control
0x14001ad8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad92  cmp     rcx, rax
0x14001ad95  jz      loc_14001AE8E
0x14001ad9b  test    [rcx+1Ch], dil
0x14001ad9f  jz      loc_14001AE8E
0x14001ada5  lea     edx, [rdi+18h]
0x14001ada8  mov     r9d, ebx
0x14001adab  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001adb2  mov     rcx, [rcx+10h]
0x14001adb6  call    WPP_SF_d
0x14001adbb  jmp     loc_14001AE8E
0x14001adc0  mov     [rbp+var_20], r14
0x14001adc4  lea     rax, [rbp+arg_10]
0x14001adc8  mov     [rbp+var_18], rax
0x14001adcc  mov     [rbp+arg_10], r14
0x14001add0  lea     rax, [rbp+var_20]
0x14001add4  mov     [rsp+50h+ppv], rax; ppv
0x14001add9  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x14001ade0  xor     edx, edx; pUnkOuter
0x14001ade2  lea     r8d, [rdx+17h]; dwClsContext
0x14001ade6  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x14001aded  call    cs:__imp_CoCreateInstance
0x14001adf3  mov     esi, eax
0x14001adf5  mov     rax, [rbp+var_20]
0x14001adf9  test    rax, rax
0x14001adfc  jz      short loc_14001AE1A
0x14001adfe  mov     rdx, [rbp+var_18]
0x14001ae02  mov     rcx, [rdx]
0x14001ae05  mov     [rdx], rax
0x14001ae08  test    rcx, rcx
0x14001ae0b  jz      short loc_14001AE1A
0x14001ae0d  mov     rdx, [rcx]
0x14001ae10  mov     rax, [rdx+10h]
0x14001ae14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae19  nop
0x14001ae1a  test    esi, esi
0x14001ae1c  jns     short loc_14001AE44
0x14001ae1e  lea     rax, WPP_GLOBAL_Control
0x14001ae25  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae2c  cmp     rcx, rax
0x14001ae2f  jz      short loc_14001AE8E
0x14001ae31  test    [rcx+1Ch], dil
0x14001ae35  jz      short loc_14001AE8E
0x14001ae37  mov     edx, 1Ah
0x14001ae3c  mov     r9d, esi
0x14001ae3f  jmp     loc_14001ADAB
0x14001ae44  mov     rcx, [rbp+arg_10]
0x14001ae48  mov     rax, [rcx]
0x14001ae4b  lea     rdx, [rbp+arg_0]
0x14001ae4f  mov     rax, [rax+60h]
0x14001ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae58  mov     r9d, eax
0x14001ae5b  test    eax, eax
0x14001ae5d  jns     short loc_14001AE82
0x14001ae5f  lea     rax, WPP_GLOBAL_Control
0x14001ae66  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae6d  cmp     rcx, rax
0x14001ae70  jz      short loc_14001AE8E
0x14001ae72  test    [rcx+1Ch], dil
0x14001ae76  jz      short loc_14001AE8E
0x14001ae78  mov     edx, 1Bh
0x14001ae7d  jmp     loc_14001ADAB
0x14001ae82  mov     edi, r14d
0x14001ae85  cmp     [rbp+arg_0], r14w
0x14001ae8a  setnz   dil
0x14001ae8e  mov     rcx, [rbp+arg_10]
0x14001ae92  test    rcx, rcx
0x14001ae95  jz      short loc_14001AEA4
0x14001ae97  mov     rax, [rcx]
0x14001ae9a  mov     rax, [rax+10h]
0x14001ae9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aea3  nop
0x14001aea4  test    ebx, ebx
0x14001aea6  js      short loc_14001AEAE
0x14001aea8  call    cs:__imp_CoUninitialize
0x14001aeae  mov     eax, edi
0x14001aeb0  add     rsp, 50h
0x14001aeb4  pop     r14
0x14001aeb6  pop     rdi
0x14001aeb7  pop     rsi
0x14001aeb8  pop     rbx
0x14001aeb9  pop     rbp
0x14001aeba  retn
```
