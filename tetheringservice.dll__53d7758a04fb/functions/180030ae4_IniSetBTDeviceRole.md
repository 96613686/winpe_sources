# IniSetBTDeviceRole

- ea: `0x180030ae4`
- end: `0x180030c0c`
- name: `IniSetBTDeviceRole`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002621c`
- `0x18002fbfc`

## callees

- `0x180002590`
- `0x180030918`
- `0x180030ae4`

## string_xrefs

- `0x180030b30`: `Network Access Point Service`
- `0x180030b37`: `Personal Ad Hoc Network Service which provides access to a network`
- `0x180030b24`: `Personal Ad Hoc User Service`

## pseudocode

```c
__int64 __fastcall IniSetBTDeviceRole(__int64 a1, unsigned int a2)
{
  const wchar_t *v5; // rax
  const wchar_t *v6; // r8
  __int64 v7; // r11
  _WORD *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  _WORD *v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // rax
  _WORD *v14; // rcx
  _BYTE v16[112]; // [rsp+20h] [rbp-218h] BYREF
  _BYTE v17[400]; // [rsp+90h] [rbp-1A8h] BYREF

  if ( a2 == 1 )
  {
    v5 = L"Network Access Point Service";
    v6 = L"Personal Ad Hoc Network Service which provides access to a network";
  }
  else
  {
    if ( a2 != 3 )
      return 50;
    v5 = L"Personal Ad Hoc User Service";
    v6 = L"Personal Ad Hoc User Service";
  }
  v7 = 2147483646;
  v8 = v16;
  v9 = 2147483646;
  v10 = 50;
  do
  {
    if ( !v9 )
      break;
    if ( !*v5 )
      break;
    *v8++ = *v5++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  if ( !v10 )
    return 1359;
  v12 = 200;
  v13 = v17;
  do
  {
    if ( !v7 )
      break;
    if ( !*v6 )
      break;
    *v13++ = *v6++;
    --v7;
    --v12;
  }
  while ( v12 );
  v14 = v13 - 1;
  if ( v12 )
    v14 = v13;
  *v14 = 0;
  if ( v12 )
    return (unsigned int)IniSetBTDeviceConfig(a1, a2, v16, v17);
  else
    return 1359;
}

```

## disassembly

```asm
0x180030ae4  mov     [rsp+arg_8], rbx
0x180030ae9  mov     [rsp+arg_10], rsi
0x180030aee  push    rdi
0x180030aef  sub     rsp, 230h
0x180030af6  mov     rax, cs:__security_cookie
0x180030afd  xor     rax, rsp
0x180030b00  mov     [rsp+238h+var_18], rax
0x180030b08  mov     rdi, rcx
0x180030b0b  mov     r10d, edx
0x180030b0e  mov     ecx, edx
0x180030b10  sub     ecx, 1
0x180030b13  jz      short loc_180030B30
0x180030b15  cmp     ecx, 2
0x180030b18  jz      short loc_180030B24
0x180030b1a  mov     edx, 32h ; '2'
0x180030b1f  jmp     loc_180030BE5
0x180030b24  lea     rax, aPersonalAdHocU; "Personal Ad Hoc User Service"
0x180030b2b  mov     r8, rax
0x180030b2e  jmp     short loc_180030B3E
0x180030b30  lea     rax, aNetworkAccessP; "Network Access Point Service"
0x180030b37  lea     r8, aPersonalAdHocN; "Personal Ad Hoc Network Service which p"...
0x180030b3e  mov     r11d, 7FFFFFFEh
0x180030b44  lea     r9, [rsp+238h+var_218]
0x180030b49  mov     ecx, r11d
0x180030b4c  mov     edx, 32h ; '2'
0x180030b51  xor     esi, esi
0x180030b53  test    rcx, rcx
0x180030b56  jz      short loc_180030B75
0x180030b58  movzx   ebx, word ptr [rax]
0x180030b5b  test    bx, bx
0x180030b5e  jz      short loc_180030B75
0x180030b60  mov     [r9], bx
0x180030b64  add     rax, 2
0x180030b68  add     r9, 2
0x180030b6c  dec     rcx
0x180030b6f  sub     rdx, 1
0x180030b73  jnz     short loc_180030B53
0x180030b75  test    rdx, rdx
0x180030b78  lea     rcx, [r9-2]
0x180030b7c  cmovnz  rcx, r9
0x180030b80  mov     [rcx], si
0x180030b83  jnz     short loc_180030B8C
0x180030b85  mov     edx, 54Fh
0x180030b8a  jmp     short loc_180030BE5
0x180030b8c  mov     edx, 0C8h
0x180030b91  lea     rax, [rsp+238h+var_1A8]
0x180030b99  test    r11, r11
0x180030b9c  jz      short loc_180030BBB
0x180030b9e  movzx   ecx, word ptr [r8]
0x180030ba2  test    cx, cx
0x180030ba5  jz      short loc_180030BBB
0x180030ba7  mov     [rax], cx
0x180030baa  add     r8, 2
0x180030bae  add     rax, 2
0x180030bb2  dec     r11
0x180030bb5  sub     rdx, 1
0x180030bb9  jnz     short loc_180030B99
0x180030bbb  test    rdx, rdx
0x180030bbe  lea     rcx, [rax-2]
0x180030bc2  cmovnz  rcx, rax
0x180030bc6  mov     [rcx], si
0x180030bc9  jz      short loc_180030B85
0x180030bcb  lea     r9, [rsp+238h+var_1A8]
0x180030bd3  mov     edx, r10d
0x180030bd6  lea     r8, [rsp+238h+var_218]
0x180030bdb  mov     rcx, rdi
0x180030bde  call    IniSetBTDeviceConfig
0x180030be3  mov     edx, eax
0x180030be5  mov     eax, edx
0x180030be7  mov     rcx, [rsp+238h+var_18]
0x180030bef  xor     rcx, rsp; StackCookie
0x180030bf2  call    __security_check_cookie
0x180030bf7  lea     r11, [rsp+238h+var_8]
0x180030bff  mov     rbx, [r11+18h]
0x180030c03  mov     rsi, [r11+20h]
0x180030c07  mov     rsp, r11
0x180030c0a  pop     rdi
0x180030c0b  retn
```
