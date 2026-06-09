# DllCanUnloadNow

- ea: `0x180008e70`
- end: `0x180008ecb`
- name: `DllCanUnloadNow`
- size: `91`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008e70`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180008e7b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180008e7b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return CUnknown::s_cActiveComponents
        || CFactory<CWPage,3>::s_cServerLocks > 0
        || CFactory<CWTask,2>::s_cServerLocks > 0
        || CFactory<CWHost,1>::s_cServerLocks > 0
        || dword_18004CE8C != 0;
  return result;
}

```

## disassembly

```asm
0x180008e70  sub     rsp, 28h
0x180008e74  lea     rcx, gPFactory; pPSFactoryBuffer
0x180008e7b  call    cs:__imp_NdrDllCanUnloadNow
0x180008e81  xor     edx, edx
0x180008e83  test    eax, eax
0x180008e85  jnz     short loc_180008EC6
0x180008e87  mov     eax, cs:?s_cActiveComponents@CUnknown@@0JA; long CUnknown::s_cActiveComponents
0x180008e8d  test    eax, eax
0x180008e8f  jnz     short loc_180008EC1
0x180008e91  cmp     cs:?s_cServerLocks@?$CFactory@VCWPage@@$02@@0JA, edx; long CFactory<CWPage,3>::s_cServerLocks
0x180008e97  jg      short loc_180008EC1
0x180008e99  test    eax, eax
0x180008e9b  jnz     short loc_180008EC1
0x180008e9d  cmp     cs:?s_cServerLocks@?$CFactory@VCWTask@@$01@@0JA, edx; long CFactory<CWTask,2>::s_cServerLocks
0x180008ea3  jg      short loc_180008EC1
0x180008ea5  test    eax, eax
0x180008ea7  jnz     short loc_180008EC1
0x180008ea9  cmp     cs:?s_cServerLocks@?$CFactory@VCWHost@@$00@@0JA, edx; long CFactory<CWHost,1>::s_cServerLocks
0x180008eaf  jg      short loc_180008EC1
0x180008eb1  cmp     cs:dword_18004CE8C, edx
0x180008eb7  lea     ecx, [rdx+1]
0x180008eba  mov     eax, edx
0x180008ebc  cmovnz  eax, ecx
0x180008ebf  jmp     short loc_180008EC6
0x180008ec1  mov     eax, 1
0x180008ec6  add     rsp, 28h
0x180008eca  retn
```
