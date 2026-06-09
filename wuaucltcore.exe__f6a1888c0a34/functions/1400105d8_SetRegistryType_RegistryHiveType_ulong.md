# SetRegistryType(RegistryHiveType,ulong *)

- ea: `0x1400105d8`
- end: `0x1400106b3`
- name: `?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z`
- size: `219`
- prototype: `int __high(enum RegistryHiveType, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001074c`
- `0x1400107fc`

## callees

- `0x140002ac0`
- `0x14000c52c`
- `0x1400105d8`

## string_xrefs

- `0x140010642`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall SetRegistryType(int a1, _DWORD *a2)
{
  int ProcessorArchitecture; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = a1;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  if ( !byte_14002F0E9 )
  {
    byte_14002F0E8 = 0;
    LOWORD(v9) = -1;
    ProcessorArchitecture = GetProcessorArchitecture((unsigned __int16 *)&v9);
    v5 = ProcessorArchitecture;
    if ( ProcessorArchitecture < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
        (const char *)(unsigned int)ProcessorArchitecture,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
        (const char *)v5,
        v7);
      return v5;
    }
    if ( (_WORD)v9 == 9 || (_WORD)v9 == 12 )
      byte_14002F0E8 = 1;
    byte_14002F0E9 = 1;
  }
  if ( byte_14002F0E8 )
    *a2 |= 0x100u;
  return 0;
}

```

## disassembly

```asm
0x1400105d8  mov     [rsp+arg_8], rbx
0x1400105dd  mov     [rsp+arg_0], ecx
0x1400105e1  push    rdi; int
0x1400105e2  sub     rsp, 20h
0x1400105e6  mov     rbx, rdx
0x1400105e9  test    rdx, rdx
0x1400105ec  jnz     short loc_140010613
0x1400105ee  mov     rcx, [rsp+28h]; this
0x1400105f3  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x1400105fa  mov     ebx, 80070057h
0x1400105ff  mov     edx, 1B4h; void *
0x140010604  mov     r9d, ebx; char *
0x140010607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001060c  mov     eax, ebx
0x14001060e  jmp     loc_1400106A8
0x140010613  cmp     cs:byte_14002F0E9, 0
0x14001061a  jnz     short loc_140010699
0x14001061c  mov     eax, 0FFFFh
0x140010621  mov     cs:byte_14002F0E8, 0
0x140010628  lea     rcx, [rsp+28h+arg_0]; unsigned __int16 *
0x14001062d  mov     word ptr [rsp+28h+arg_0], ax
0x140010632  call    ?GetProcessorArchitecture@@YAJPEAG@Z; GetProcessorArchitecture(ushort *)
0x140010637  mov     edi, eax
0x140010639  test    eax, eax
0x14001063b  jns     short loc_140010673
0x14001063d  mov     rcx, [rsp+28h]; this
0x140010642  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010649  mov     r9d, eax; char *
0x14001064c  mov     edx, 0FCh; void *
0x140010651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010656  mov     rcx, [rsp+28h]; this
0x14001065b  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x140010662  mov     r9d, edi; char *
0x140010665  mov     edx, 1C1h; void *
0x14001066a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001066f  mov     eax, edi
0x140010671  jmp     short loc_1400106A8
0x140010673  mov     eax, 9
0x140010678  cmp     ax, word ptr [rsp+28h+arg_0]
0x14001067d  jz      short loc_14001068B
0x14001067f  mov     eax, 0Ch
0x140010684  cmp     ax, word ptr [rsp+28h+arg_0]
0x140010689  jnz     short loc_140010692
0x14001068b  mov     cs:byte_14002F0E8, 1
0x140010692  mov     cs:byte_14002F0E9, 1
0x140010699  cmp     cs:byte_14002F0E8, 0
0x1400106a0  jz      short loc_1400106A6
0x1400106a2  bts     dword ptr [rbx], 8
0x1400106a6  xor     eax, eax
0x1400106a8  mov     rbx, [rsp+28h+arg_8]
0x1400106ad  add     rsp, 20h
0x1400106b1  pop     rdi
0x1400106b2  retn
```
