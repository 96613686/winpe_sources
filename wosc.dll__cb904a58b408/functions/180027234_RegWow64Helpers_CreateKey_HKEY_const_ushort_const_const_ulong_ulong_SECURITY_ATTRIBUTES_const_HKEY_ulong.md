# RegWow64Helpers::CreateKey(HKEY__ * const,ushort const * const,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x180027234`
- end: `0x180027289`
- name: `?CreateKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `85`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *const, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027064`
- `0x18002a36c`
- `0x18004f4dc`
- `0x180051190`

## callees

- `0x180027234`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027272`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027272`

## pseudocode

```c
LSTATUS __fastcall RegWow64Helpers::CreateKey(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        int a4,
        struct _SECURITY_ATTRIBUTES *const a5,
        HKEY *a6,
        unsigned int *a7)
{
  LSTATUS result; // eax

  result = RegCreateKeyExW(a1, a2, 0, 0, 0, a4 | 0x100, 0, a6, a7);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180027234  mov     r11, rsp
0x180027237  sub     rsp, 58h
0x18002723b  mov     rax, [rsp+58h+arg_30]
0x180027243  bts     r9d, 8
0x180027248  mov     [r11-18h], rax
0x18002724c  xor     r8d, r8d; Reserved
0x18002724f  mov     rax, [rsp+58h+arg_28]
0x180027257  mov     [r11-20h], rax
0x18002725b  mov     qword ptr [r11-28h], 0
0x180027263  mov     [r11-30h], r9d
0x180027267  xor     r9d, r9d; lpClass
0x18002726a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180027272  call    cs:__imp_RegCreateKeyExW
0x180027278  test    eax, eax
0x18002727a  jle     short loc_180027284
0x18002727c  movzx   eax, ax
0x18002727f  or      eax, 80070000h
0x180027284  add     rsp, 58h
0x180027288  retn
```
