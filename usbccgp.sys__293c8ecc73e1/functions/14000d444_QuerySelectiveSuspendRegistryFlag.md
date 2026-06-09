# QuerySelectiveSuspendRegistryFlag

- ea: `0x14000d444`
- end: `0x14000d562`
- name: `QuerySelectiveSuspendRegistryFlag`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140010650`

## callees

- `0x1400088b4`
- `0x14000d444`
- `0x14002e100`

## pseudocode

```c
__int64 __fastcall QuerySelectiveSuspendRegistryFlag(__int64 a1)
{
  struct _DEVICE_OBJECT *v1; // rdi
  int v3; // edx
  __int64 result; // rax
  int v5; // edx
  ULONG v6; // [rsp+30h] [rbp-28h]
  ULONG v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+68h] [rbp+10h] BYREF

  v1 = *(struct _DEVICE_OBJECT **)(a1 + 224);
  LOBYTE(v6) = 0;
  v9 = 0;
  v8 = 0;
  if ( (int)GetPdoRegistryParameter(v1, L"DeviceSelectiveSuspended", 0, 0, 0, 0, v6) >= 0 )
  {
    *(_BYTE *)(a1 + 300) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v3) = 5;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 392), v3, 1, 59, (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids);
      }
    }
  }
  LOBYTE(v7) = 0;
  result = GetPdoRegistryParameter(v1, L"SelSuspCancelBehavior", &v9, 4u, &v8, 0, v7);
  if ( (int)result >= 0 && v8 == 4 && v9 )
  {
    *(_BYTE *)(a1 + 301) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      return WPP_RECORDER_SF_(
               *(_QWORD *)(a1 + 392),
               v5,
               1,
               60,
               (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d444  mov     rax, rsp
0x14000d447  mov     [rax+18h], rbx
0x14000d44b  mov     [rax+20h], rsi
0x14000d44f  push    rdi
0x14000d450  push    r14
0x14000d452  push    r15
0x14000d454  sub     rsp, 40h
0x14000d458  mov     rdi, [rcx+0E0h]
0x14000d45f  lea     rdx, aDeviceselectiv; "DeviceSelectiveSuspended"
0x14000d466  xor     esi, esi
0x14000d468  mov     rbx, rcx
0x14000d46b  mov     [rax-28h], sil
0x14000d46f  xor     r9d, r9d
0x14000d472  mov     [rax-30h], rsi
0x14000d476  xor     r8d, r8d
0x14000d479  mov     rcx, rdi
0x14000d47c  mov     [rax-38h], rsi
0x14000d480  mov     [rax+10h], esi
0x14000d483  mov     [rax+8], esi
0x14000d486  call    GetPdoRegistryParameter
0x14000d48b  lea     r15, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000d492  lea     r14, WPP_RECORDER_INITIALIZED
0x14000d499  test    eax, eax
0x14000d49b  jns     short loc_14000D4E4
0x14000d49d  mov     byte ptr [rsp+58h+var_28], sil
0x14000d4a2  lea     rax, [rsp+58h+arg_0]
0x14000d4a7  mov     [rsp+58h+var_30], rsi
0x14000d4ac  lea     r8, [rsp+58h+arg_8]
0x14000d4b1  mov     r9d, 4
0x14000d4b7  mov     [rsp+58h+var_38], rax
0x14000d4bc  lea     rdx, aSelsuspcancelb; "SelSuspCancelBehavior"
0x14000d4c3  mov     rcx, rdi
0x14000d4c6  call    GetPdoRegistryParameter
0x14000d4cb  test    eax, eax
0x14000d4cd  jns     short loc_14000D523
0x14000d4cf  mov     rbx, [rsp+58h+arg_10]
0x14000d4d4  mov     rsi, [rsp+58h+arg_18]
0x14000d4d9  add     rsp, 40h
0x14000d4dd  pop     r15
0x14000d4df  pop     r14
0x14000d4e1  pop     rdi
0x14000d4e2  retn
0x14000d4e4  mov     byte ptr [rbx+12Ch], 1
0x14000d4eb  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000d4f2  jz      short loc_14000D49D
0x14000d4f4  mov     rax, cs:WPP_GLOBAL_Control
0x14000d4fb  cmp     [rax+48h], si
0x14000d4ff  jz      short loc_14000D49D
0x14000d501  mov     rcx, [rbx+188h]
0x14000d508  mov     r9d, 3Bh ; ';'
0x14000d50e  mov     dl, 5
0x14000d510  mov     [rsp+58h+var_38], r15
0x14000d515  lea     r8d, [r9-3Ah]
0x14000d519  call    WPP_RECORDER_SF_
0x14000d51e  jmp     loc_14000D49D
0x14000d523  cmp     [rsp+58h+arg_0], 4
0x14000d528  jnz     short loc_14000D4CF
0x14000d52a  cmp     [rsp+58h+arg_8], esi
0x14000d52e  jz      short loc_14000D4CF
0x14000d530  mov     [rbx+12Dh], sil
0x14000d537  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000d53e  jz      short loc_14000D4CF
0x14000d540  mov     rcx, [rbx+188h]
0x14000d547  mov     r9d, 3Ch ; '<'
0x14000d54d  mov     dl, 4
0x14000d54f  mov     [rsp+58h+var_38], r15
0x14000d554  lea     r8d, [r9-3Bh]
0x14000d558  call    WPP_RECORDER_SF_
0x14000d55d  jmp     loc_14000D4CF
```
