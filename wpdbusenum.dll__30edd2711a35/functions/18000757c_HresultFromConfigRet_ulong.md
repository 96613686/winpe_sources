# HresultFromConfigRet(ulong)

- ea: `0x18000757c`
- end: `0x18000759c`
- name: `?HresultFromConfigRet@@YAJK@Z`
- size: `32`
- prototype: `signed int __fastcall(CONFIGRET)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800074b4`
- `0x180011008`

## callees

- `0x18000757c`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180007585`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180007585`

## pseudocode

```c
signed int __fastcall HresultFromConfigRet(CONFIGRET a1)
{
  signed int result; // eax

  result = CM_MapCrToWin32Err(a1, 0xDu);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000757c  sub     rsp, 28h
0x180007580  mov     edx, 0Dh; DefaultErr
0x180007585  call    cs:__imp_CM_MapCrToWin32Err
0x18000758b  test    eax, eax
0x18000758d  jle     short loc_180007597
0x18000758f  movzx   eax, ax
0x180007592  or      eax, 80070000h
0x180007597  add     rsp, 28h
0x18000759b  retn
```
