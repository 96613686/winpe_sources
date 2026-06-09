# SmpConfigurePagefileOptions

- ea: `0x140013810`
- end: `0x140013826`
- name: `SmpConfigurePagefileOptions`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013810`

## pseudocode

```c
__int64 __fastcall SmpConfigurePagefileOptions(__int64 a1, __int64 a2, int *a3, int a4)
{
  int v4; // eax

  if ( a4 == 4 )
    v4 = *a3;
  else
    v4 = 0;
  SmpPagefileOnOsVolume = v4;
  return 0;
}

```

## disassembly

```asm
0x140013810  cmp     r9d, 4
0x140013814  jz      short loc_14001381A
0x140013816  xor     eax, eax
0x140013818  jmp     short loc_14001381D
0x14001381a  mov     eax, [r8]
0x14001381d  mov     cs:SmpPagefileOnOsVolume, eax
0x140013823  xor     eax, eax
0x140013825  retn
```
