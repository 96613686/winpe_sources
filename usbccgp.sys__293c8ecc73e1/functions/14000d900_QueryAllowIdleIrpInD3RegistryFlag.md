# QueryAllowIdleIrpInD3RegistryFlag

- ea: `0x14000d900`
- end: `0x14000d9ab`
- name: `QueryAllowIdleIrpInD3RegistryFlag`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140010650`

## callees

- `0x1400088b4`
- `0x14000d900`
- `0x14002e100`

## pseudocode

```c
PDEVICE_OBJECT __fastcall QueryAllowIdleIrpInD3RegistryFlag(__int64 a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  PDEVICE_OBJECT result; // rax
  int v4; // edx
  ULONG v5; // [rsp+30h] [rbp-18h]
  int v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(struct _DEVICE_OBJECT **)(a1 + 224);
  LOBYTE(v5) = 0;
  v7 = 0;
  v6 = 0;
  result = (PDEVICE_OBJECT)GetPdoRegistryParameter(v2, L"AllowIdleIrpInD3", &v7, 4u, &v6, 0, v5);
  if ( (int)result >= 0 && v6 == 4 )
  {
    if ( v7 )
    {
      *(_BYTE *)(a1 + 302) = 1;
      result = (PDEVICE_OBJECT)&WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        result = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v4) = 5;
          return (PDEVICE_OBJECT)WPP_RECORDER_SF_(
                                   *(_QWORD *)(a1 + 392),
                                   v4,
                                   1,
                                   61,
                                   (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d900  mov     rax, rsp
0x14000d903  mov     [rax+18h], rbx
0x14000d907  push    rdi
0x14000d908  sub     rsp, 40h
0x14000d90c  xor     edi, edi
0x14000d90e  mov     rbx, rcx
0x14000d911  mov     rcx, [rcx+0E0h]
0x14000d918  lea     r8, [rsp+48h+arg_8]
0x14000d91d  mov     [rax-18h], dil
0x14000d921  lea     rdx, aAllowidleirpin; "AllowIdleIrpInD3"
0x14000d928  mov     [rax-20h], rdi
0x14000d92c  mov     [rax+10h], edi
0x14000d92f  lea     r9d, [rdi+4]
0x14000d933  mov     [rax+8], edi
0x14000d936  lea     rax, [rax+8]
0x14000d93a  mov     [rsp+48h+var_28], rax
0x14000d93f  call    GetPdoRegistryParameter
0x14000d944  test    eax, eax
0x14000d946  jns     short loc_14000D954
0x14000d948  mov     rbx, [rsp+48h+arg_10]
0x14000d94d  add     rsp, 40h
0x14000d951  pop     rdi
0x14000d952  retn
0x14000d954  cmp     [rsp+48h+arg_0], 4
0x14000d959  jnz     short loc_14000D948
0x14000d95b  cmp     [rsp+48h+arg_8], edi
0x14000d95f  jz      short loc_14000D948
0x14000d961  mov     byte ptr [rbx+12Eh], 1
0x14000d968  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d96f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d976  jz      short loc_14000D948
0x14000d978  mov     rax, cs:WPP_GLOBAL_Control
0x14000d97f  cmp     [rax+48h], di
0x14000d983  jz      short loc_14000D948
0x14000d985  mov     rcx, [rbx+188h]
0x14000d98c  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000d993  mov     r9d, 3Dh ; '='
0x14000d999  mov     [rsp+48h+var_28], rax
0x14000d99e  mov     dl, 5
0x14000d9a0  lea     r8d, [r9-3Ch]
0x14000d9a4  call    WPP_RECORDER_SF_
0x14000d9a9  jmp     short loc_14000D948
```
