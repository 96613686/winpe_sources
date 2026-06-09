# CompatCacheSetFusionState

- ea: `0x180005830`
- end: `0x180005915`
- name: `CompatCacheSetFusionState`
- size: `229`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, __int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x180005830`
- `0x180006c13`
- `0x180007010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18000589f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000589f`

## pseudocode

```c
NTSTATUS __fastcall CompatCacheSetFusionState(PCWSTR SourceString, __int64 a2, int a3, int a4)
{
  int v8; // eax
  NTSTATUS result; // eax
  _BYTE v10[96]; // [rsp+20h] [rbp-1A8h] BYREF
  int v11; // [rsp+80h] [rbp-148h]
  __int64 v12; // [rsp+98h] [rbp-130h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-128h] BYREF
  int *v14; // [rsp+B0h] [rbp-118h]
  int v15; // [rsp+B8h] [rbp-110h]
  int v16; // [rsp+1E0h] [rbp+18h] BYREF

  v16 = 0;
  memset_0(v10, 0, 0x188u);
  v8 = 0;
  if ( a3 )
  {
    v8 = 1;
    v16 = 1;
  }
  if ( a4 )
    v16 = v8 | 2;
  v11 = 32;
  if ( a2 == -1 )
    a2 = 0;
  v12 = a2;
  result = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( result >= 0 )
  {
    v15 = 4;
    v14 = &v16;
    return ((__int64 (__fastcall *)(__int64, _BYTE *))g_CompatCacheServiceApi)(2, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180005830  mov     [rsp+arg_0], rbx
0x180005835  mov     [rsp+arg_8], rbp
0x18000583a  push    rsi
0x18000583b  push    rdi
0x18000583c  push    r14
0x18000583e  sub     rsp, 1B0h
0x180005845  mov     edi, r8d
0x180005848  mov     rbx, rdx
0x18000584b  mov     rbp, rcx
0x18000584e  xor     r14d, r14d
0x180005851  xor     edx, edx; Val
0x180005853  mov     [rsp+1C8h+arg_10], r14d
0x18000585b  mov     r8d, 188h; Size
0x180005861  lea     rcx, [rsp+1C8h+var_1A8]; void *
0x180005866  mov     esi, r9d
0x180005869  call    memset_0
0x18000586e  mov     eax, r14d
0x180005871  test    edi, edi
0x180005873  jnz     short loc_1800058C8
0x180005875  test    esi, esi
0x180005877  jnz     short loc_1800058D6
0x180005879  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000587d  mov     [rsp+1C8h+var_148], 20h ; ' '
0x180005888  mov     rdx, rbp; SourceString
0x18000588b  lea     rcx, [rsp+1C8h+DestinationString]; DestinationString
0x180005893  cmovz   rbx, r14
0x180005897  mov     [rsp+1C8h+var_130], rbx
0x18000589f  call    cs:__imp_RtlInitUnicodeStringEx
0x1800058a6  nop     dword ptr [rax+rax+00h]
0x1800058ab  test    eax, eax
0x1800058ad  jns     short loc_1800058E2
0x1800058af  lea     r11, [rsp+1C8h+var_18]
0x1800058b7  mov     rbx, [r11+20h]
0x1800058bb  mov     rbp, [r11+28h]
0x1800058bf  mov     rsp, r11
0x1800058c2  pop     r14
0x1800058c4  pop     rdi
0x1800058c5  pop     rsi
0x1800058c6  retn
0x1800058c8  mov     eax, 1
0x1800058cd  mov     [rsp+1C8h+arg_10], eax
0x1800058d4  jmp     short loc_180005875
0x1800058d6  or      eax, 2
0x1800058d9  mov     [rsp+1C8h+arg_10], eax
0x1800058e0  jmp     short loc_180005879
0x1800058e2  lea     rax, [rsp+1C8h+arg_10]
0x1800058ea  mov     [rsp+1C8h+var_110], 4
0x1800058f5  mov     [rsp+1C8h+var_118], rax
0x1800058fd  lea     rdx, [rsp+1C8h+var_1A8]
0x180005902  mov     rax, cs:g_CompatCacheServiceApi
0x180005909  mov     ecx, 2
0x18000590e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005913  jmp     short loc_1800058AF
```
