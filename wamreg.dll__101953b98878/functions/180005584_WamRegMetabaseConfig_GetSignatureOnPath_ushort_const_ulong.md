# WamRegMetabaseConfig::GetSignatureOnPath(ushort const *,ulong *)

- ea: `0x180005584`
- end: `0x18000564e`
- name: `?GetSignatureOnPath@WamRegMetabaseConfig@@QEAAJPEBGPEAK@Z`
- size: `202`
- prototype: `int(WamRegMetabaseConfig *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800034b0`

## callees

- `0x180005584`
- `0x180005a50`
- `0x180005b90`
- `0x180006660`
- `0x180006850`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::GetSignatureOnPath(
        WamRegMetabaseConfig *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  int v3; // ebx
  WamRegMetabaseConfig *v6; // rcx
  int v7; // r11d
  WamRegMetabaseConfig *v8; // rcx
  unsigned int v9; // r8d
  WamRegMetabaseConfig *v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  WamRegMetabaseConfig *v13; // rcx
  unsigned int v14; // r8d
  int v15; // r10d
  int v16; // r10d
  unsigned int v17; // eax
  int v18; // r10d
  __int64 result; // rax
  unsigned int v20[4]; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int16 v21[40]; // [rsp+40h] [rbp-B8h] BYREF
  unsigned __int16 v22[40]; // [rsp+90h] [rbp-68h] BYREF

  v3 = 0;
  v20[0] = 0;
  v7 = WamRegMetabaseConfig::MDGetDWORD(this, a2, (__int64)a3, v20);
  if ( v7 >= 0 )
  {
    v7 = WamRegMetabaseConfig::MDGetIDs(v6, a2, v21, v22, v20[0]);
    if ( v7 >= 0 )
    {
      WamRegMetabaseConfig::WamRegChkSum(v8, a2, v9);
      v12 = WamRegMetabaseConfig::WamRegChkSum(v10, v21, v11);
      v16 = v12 ^ v15;
      if ( v20[0] == 1 )
      {
        v17 = WamRegMetabaseConfig::WamRegChkSum(v13, v22, v14);
        v3 = v18 ^ v17;
      }
      else
      {
        v3 = v16;
      }
    }
  }
  result = 0;
  if ( v7 < 0 )
    v3 = 0;
  *a3 = v3;
  return result;
}

```

## disassembly

```asm
0x180005584  mov     [rsp+arg_0], rbx
0x180005589  mov     [rsp+arg_18], rsi
0x18000558e  push    rdi
0x18000558f  sub     rsp, 0F0h
0x180005596  mov     rax, cs:__security_cookie
0x18000559d  xor     rax, rsp
0x1800055a0  mov     [rsp+0F8h+var_18], rax
0x1800055a8  xor     ebx, ebx
0x1800055aa  lea     r9, [rsp+0F8h+var_C8]; unsigned int *
0x1800055af  mov     [rsp+0F8h+var_C8], ebx
0x1800055b3  mov     rsi, r8
0x1800055b6  mov     rdi, rdx
0x1800055b9  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x1800055be  mov     r11d, eax
0x1800055c1  test    eax, eax
0x1800055c3  js      short loc_18000561F
0x1800055c5  mov     eax, [rsp+0F8h+var_C8]
0x1800055c9  lea     r9, [rsp+0F8h+var_68]; unsigned __int16 *
0x1800055d1  lea     r8, [rsp+0F8h+var_B8]; unsigned __int16 *
0x1800055d6  mov     [rsp+0F8h+var_D8], eax; unsigned int
0x1800055da  mov     rdx, rdi; unsigned __int16 *
0x1800055dd  call    ?MDGetIDs@WamRegMetabaseConfig@@QEAAJPEBGPEAG1K@Z; WamRegMetabaseConfig::MDGetIDs(ushort const *,ushort *,ushort *,ulong)
0x1800055e2  mov     r11d, eax
0x1800055e5  test    eax, eax
0x1800055e7  js      short loc_18000561F
0x1800055e9  mov     rdx, rdi; unsigned __int16 *
0x1800055ec  call    ?WamRegChkSum@WamRegMetabaseConfig@@AEAAKPEBGK@Z; WamRegMetabaseConfig::WamRegChkSum(ushort const *,ulong)
0x1800055f1  lea     rdx, [rsp+0F8h+var_B8]; unsigned __int16 *
0x1800055f6  mov     r10d, eax
0x1800055f9  call    ?WamRegChkSum@WamRegMetabaseConfig@@AEAAKPEBGK@Z; WamRegMetabaseConfig::WamRegChkSum(ushort const *,ulong)
0x1800055fe  xor     r10d, eax
0x180005601  cmp     [rsp+0F8h+var_C8], 1
0x180005606  jnz     short loc_18000561C
0x180005608  lea     rdx, [rsp+0F8h+var_68]; unsigned __int16 *
0x180005610  call    ?WamRegChkSum@WamRegMetabaseConfig@@AEAAKPEBGK@Z; WamRegMetabaseConfig::WamRegChkSum(ushort const *,ulong)
0x180005615  mov     ebx, eax
0x180005617  xor     ebx, r10d
0x18000561a  jmp     short loc_18000561F
0x18000561c  mov     ebx, r10d
0x18000561f  xor     eax, eax
0x180005621  test    r11d, r11d
0x180005624  cmovs   ebx, eax
0x180005627  mov     [rsi], ebx
0x180005629  mov     rcx, [rsp+0F8h+var_18]
0x180005631  xor     rcx, rsp; StackCookie
0x180005634  call    __security_check_cookie
0x180005639  lea     r11, [rsp+0F8h+var_8]
0x180005641  mov     rbx, [r11+10h]
0x180005645  mov     rsi, [r11+28h]
0x180005649  mov     rsp, r11
0x18000564c  pop     rdi
0x18000564d  retn
```
