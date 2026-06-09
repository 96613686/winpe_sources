# SqospGetParametersUINT32

- ea: `0x140013e70`
- end: `0x140014038`
- name: `SqospGetParametersUINT32`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013e18`
- `0x1400161ec`

## callees

- `0x14000666c`
- `0x140008d20`
- `0x140013e70`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140014003`
- `ntoskrnl!ZwClose` at `0x140014003`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140013f23`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140013f23`
- `ntoskrnl!ZwQueryValueKey` at `0x140013fc8`
- `ntoskrnl!ZwQueryValueKey` at `0x140013fc8`

## pseudocode

```c
char __fastcall SqospGetParametersUINT32(__int64 a1, WCHAR *a2, unsigned int a3, unsigned int a4, unsigned int *a5)
{
  char v8; // r14
  __int64 v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // r9
  __int16 v12; // cx
  int v13; // eax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-30h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-20h] BYREF
  int v22; // [rsp+54h] [rbp-1Ch]
  int v23; // [rsp+58h] [rbp-18h]
  unsigned int v24; // [rsp+5Ch] [rbp-14h]

  ResultLength = 0;
  KeyHandle = 0;
  v8 = 0;
  ValueName = 0;
  if ( a2 )
  {
    v9 = 0x7FFF;
    v10 = a2;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = v9 == 0 ? 0xC000000D : 0;
    if ( !v9 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return v8;
      }
      v15 = 12;
      goto LABEL_16;
    }
    v12 = 2 * v9;
    ValueName.Buffer = a2;
    ValueName.Length = -2 - v12;
    ValueName.MaximumLength = -v12;
  }
  v13 = IoOpenDriverRegistryKey(a1, 0, 131097, 0, &KeyHandle);
  v11 = (unsigned int)v13;
  if ( v13 >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
      && v22 == 4
      && v23 == 4 )
    {
      v16 = v24;
      *a5 = v24;
      if ( v16 >= a3 )
      {
        if ( v16 > a4 )
          *a5 = a4;
      }
      else
      {
        *a5 = a3;
      }
      v8 = 1;
    }
    goto LABEL_25;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v15 = 13;
LABEL_16:
    WPP_SF_d(v14->AttachedDevice, v15, WPP_b8a405419f5733ac566e8c3690148060_Traceguids, v11);
  }
LABEL_25:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v8;
}

```

## disassembly

```asm
0x140013e70  mov     [rsp-28h+arg_8], rbx
0x140013e75  mov     [rsp-28h+arg_10], rsi
0x140013e7a  push    rbp
0x140013e7b  push    rdi
0x140013e7c  push    r12
0x140013e7e  push    r14
0x140013e80  push    r15
0x140013e82  mov     rbp, rsp
0x140013e85  sub     rsp, 70h
0x140013e89  mov     rax, cs:__security_cookie
0x140013e90  xor     rax, rsp
0x140013e93  mov     [rbp+var_8], rax
0x140013e97  mov     rbx, [rbp+arg_20]
0x140013e9b  xor     r15d, r15d
0x140013e9e  mov     [rbp+var_40], r15d
0x140013ea2  xorps   xmm0, xmm0
0x140013ea5  mov     [rbp+KeyHandle], r15
0x140013ea9  mov     edi, r9d
0x140013eac  mov     esi, r8d
0x140013eaf  mov     r10, rcx
0x140013eb2  lea     r12d, [r15+2]
0x140013eb6  mov     r14b, r15b
0x140013eb9  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140013ebd  test    rdx, rdx
0x140013ec0  jz      short loc_140013F0C
0x140013ec2  mov     ecx, 7FFFh
0x140013ec7  mov     rax, rdx
0x140013eca  cmp     [rax], r15w
0x140013ece  jz      short loc_140013ED9
0x140013ed0  add     rax, r12
0x140013ed3  sub     rcx, 1
0x140013ed7  jnz     short loc_140013ECA
0x140013ed9  mov     rax, rcx
0x140013edc  neg     rax
0x140013edf  sbb     r9d, r9d
0x140013ee2  not     r9d
0x140013ee5  and     r9d, 0C000000Dh
0x140013eec  test    rcx, rcx
0x140013eef  jz      short loc_140013F69
0x140013ef1  add     cx, cx
0x140013ef4  mov     [rbp+ValueName.Buffer], rdx
0x140013ef8  mov     eax, 0FFFEh
0x140013efd  sub     ax, cx
0x140013f00  mov     [rbp+ValueName.Length], ax
0x140013f04  add     ax, r12w
0x140013f08  mov     [rbp+ValueName.MaximumLength], ax
0x140013f0c  lea     rax, [rbp+KeyHandle]
0x140013f10  xor     r9d, r9d
0x140013f13  xor     edx, edx
0x140013f15  mov     qword ptr [rsp+70h+Length], rax
0x140013f1a  mov     r8d, 20019h
0x140013f20  mov     rcx, r10
0x140013f23  call    cs:__imp_IoOpenDriverRegistryKey
0x140013f2a  nop     dword ptr [rax+rax+00h]
0x140013f2f  mov     r9d, eax
0x140013f32  test    eax, eax
0x140013f34  jns     short loc_140013FA8
0x140013f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f3d  lea     rax, WPP_GLOBAL_Control
0x140013f44  cmp     rcx, rax
0x140013f47  jz      loc_140013FFA
0x140013f4d  mov     eax, [rcx+2Ch]
0x140013f50  test    al, al
0x140013f52  jns     loc_140013FFA
0x140013f58  cmp     [rcx+29h], r12b
0x140013f5c  jb      loc_140013FFA
0x140013f62  mov     edx, 0Dh
0x140013f67  jmp     short loc_140013F96
0x140013f69  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f70  lea     rax, WPP_GLOBAL_Control
0x140013f77  cmp     rcx, rax
0x140013f7a  jz      loc_14001400F
0x140013f80  mov     eax, [rcx+2Ch]
0x140013f83  test    al, al
0x140013f85  jns     loc_14001400F
0x140013f8b  cmp     [rcx+29h], r12b
0x140013f8f  jb      short loc_14001400F
0x140013f91  mov     edx, 0Ch
0x140013f96  mov     rcx, [rcx+18h]
0x140013f9a  lea     r8, WPP_b8a405419f5733ac566e8c3690148060_Traceguids
0x140013fa1  call    WPP_SF_d
0x140013fa6  jmp     short loc_140013FFA
0x140013fa8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013fac  lea     rax, [rbp+var_40]
0x140013fb0  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140013fb5  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x140013fb9  mov     r8d, r12d; KeyValueInformationClass
0x140013fbc  mov     [rsp+70h+Length], 14h; Length
0x140013fc4  lea     rdx, [rbp+ValueName]; ValueName
0x140013fc8  call    cs:__imp_ZwQueryValueKey
0x140013fcf  nop     dword ptr [rax+rax+00h]
0x140013fd4  test    eax, eax
0x140013fd6  js      short loc_140013FFA
0x140013fd8  cmp     [rbp+var_1C], 4
0x140013fdc  jnz     short loc_140013FFA
0x140013fde  cmp     [rbp+var_18], 4
0x140013fe2  jnz     short loc_140013FFA
0x140013fe4  mov     eax, [rbp+var_14]
0x140013fe7  mov     [rbx], eax
0x140013fe9  cmp     eax, esi
0x140013feb  jnb     short loc_140013FF1
0x140013fed  mov     [rbx], esi
0x140013fef  jmp     short loc_140013FF7
0x140013ff1  cmp     eax, edi
0x140013ff3  jbe     short loc_140013FF7
0x140013ff5  mov     [rbx], edi
0x140013ff7  mov     r14b, 1
0x140013ffa  mov     rcx, [rbp+KeyHandle]; Handle
0x140013ffe  test    rcx, rcx
0x140014001  jz      short loc_14001400F
0x140014003  call    cs:__imp_ZwClose
0x14001400a  nop     dword ptr [rax+rax+00h]
0x14001400f  mov     al, r14b
0x140014012  mov     rcx, [rbp+var_8]
0x140014016  xor     rcx, rsp; StackCookie
0x140014019  call    __security_check_cookie
0x14001401e  lea     r11, [rsp+70h+var_s0]
0x140014023  mov     rbx, [r11+38h]
0x140014027  mov     rsi, [r11+40h]
0x14001402b  mov     rsp, r11
0x14001402e  pop     r15
0x140014030  pop     r14
0x140014032  pop     r12
0x140014034  pop     rdi
0x140014035  pop     rbp
0x140014036  retn
```
