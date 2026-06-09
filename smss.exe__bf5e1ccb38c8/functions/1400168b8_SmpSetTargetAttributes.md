# SmpSetTargetAttributes

- ea: `0x1400168b8`
- end: `0x140016950`
- name: `SmpSetTargetAttributes`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140013fd8`
- `0x14001426c`
- `0x140016b94`

## callees

- `0x140003114`
- `0x1400168b8`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x140016908`
- `ntdll!NtSetInformationFile` at `0x140016908`

## pseudocode

```c
__int64 __fastcall SmpSetTargetAttributes(void *a1, unsigned int a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  struct _IO_STATUS_BLOCK v6; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v7[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+60h] [rbp-18h]
  int v9; // [rsp+64h] [rbp-14h]

  memset(v7, 0, sizeof(v7));
  v9 = 0;
  v6 = 0;
  v8 = a2;
  v3 = NtSetInformationFile(a1, &v6, v7, 0x28u, FileBasicInformation);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  else
    SmLogFailureInt((__int64)"SmpSetTargetAttributes", 0x18B4u, a2, 0, v3);
  return v4;
}

```

## disassembly

```asm
0x1400168b8  mov     r11, rsp
0x1400168bb  mov     [r11+18h], rbx
0x1400168bf  push    rdi
0x1400168c0  sub     rsp, 70h
0x1400168c4  mov     rax, cs:__security_cookie
0x1400168cb  xor     rax, rsp
0x1400168ce  mov     [rsp+78h+var_10], rax
0x1400168d3  xor     eax, eax
0x1400168d5  mov     edi, edx
0x1400168d7  xorps   xmm1, xmm1
0x1400168da  mov     [rsp+78h+FileInformationClass], 4; FileInformationClass
0x1400168e2  xorps   xmm0, xmm0
0x1400168e5  lea     r8, [r11-38h]; FileInformation
0x1400168e9  movups  [rsp+78h+var_38], xmm1
0x1400168ee  lea     r9d, [rax+28h]; Length
0x1400168f2  movups  [rsp+78h+var_28], xmm1
0x1400168f7  mov     [r11-18h], rax
0x1400168fb  lea     rdx, [r11-48h]; IoStatusBlock
0x1400168ff  movups  [rsp+78h+var_48], xmm0
0x140016904  mov     [rsp+78h+var_18], edi
0x140016908  call    cs:__imp_NtSetInformationFile
0x14001690e  mov     ebx, eax
0x140016910  test    eax, eax
0x140016912  jns     short loc_140016931
0x140016914  mov     r8d, edi
0x140016917  mov     [rsp+78h+FileInformationClass], eax
0x14001691b  xor     r9d, r9d
0x14001691e  lea     rcx, aSmpsettargetat; "SmpSetTargetAttributes"
0x140016925  mov     edx, 18B4h
0x14001692a  call    SmLogFailureInt
0x14001692f  jmp     short loc_140016933
0x140016931  xor     ebx, ebx
0x140016933  mov     eax, ebx
0x140016935  mov     rcx, [rsp+78h+var_10]
0x14001693a  xor     rcx, rsp; StackCookie
0x14001693d  call    __security_check_cookie
0x140016942  mov     rbx, [rsp+78h+arg_10]
0x14001694a  add     rsp, 70h
0x14001694e  pop     rdi
0x14001694f  retn
```
