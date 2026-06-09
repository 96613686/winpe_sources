# MsaTracingInternal::TraceFunctionExit(char const *,long)

- ea: `0x180008f6c`
- end: `0x180008fcd`
- name: `?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z`
- size: `97`
- prototype: `__int64 __fastcall(MsaTracingInternal *this, const char *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054dc`
- `0x18000578c`
- `0x180006410`
- `0x18000a26c`
- `0x18000b5b4`
- `0x18000b820`
- `0x18000b9e0`
- `0x18000bac0`
- `0x18000bbf8`

## callees

- `0x180008f6c`
- `0x1800099a8`

## pseudocode

```c
__int64 __fastcall MsaTracingInternal::TraceFunctionExit(MsaTracingInternal *this, const char *a2)
{
  __int64 *v2; // rdx

  if ( dword_180020A0C == 1 )
  {
    if ( (byte_180020581 & 4) != 0 )
    {
      v2 = LiveSsp_TraceFunction_Exit;
      return McTemplateU0sd_EventWriteTransfer(this, v2, this);
    }
  }
  else if ( dword_180020A0C == 2 )
  {
    if ( (byte_180020582 & 4) != 0 )
    {
      v2 = CredProv_TraceFunction_Exit;
      return McTemplateU0sd_EventWriteTransfer(this, v2, this);
    }
  }
  else if ( dword_180020A0C == 3 && (byte_180020583 & 4) != 0 )
  {
    v2 = WlidNsp_TraceFunction_Exit;
    return McTemplateU0sd_EventWriteTransfer(this, v2, this);
  }
  return 0;
}

```

## disassembly

```asm
0x180008f6c  mov     r8d, cs:dword_180020A0C
0x180008f73  sub     r8d, 1
0x180008f77  jz      short loc_180008FAF
0x180008f79  sub     r8d, 1
0x180008f7d  jz      short loc_180008F9A
0x180008f7f  cmp     r8d, 1
0x180008f83  jnz     short loc_180008FCA
0x180008f85  test    cs:byte_180020583, 4
0x180008f8c  jz      short loc_180008FCA
0x180008f8e  mov     r9d, edx
0x180008f91  lea     rdx, WlidNsp_TraceFunction_Exit
0x180008f98  jmp     short loc_180008FC2
0x180008f9a  test    cs:byte_180020582, 4
0x180008fa1  jz      short loc_180008FCA
0x180008fa3  mov     r9d, edx
0x180008fa6  lea     rdx, CredProv_TraceFunction_Exit
0x180008fad  jmp     short loc_180008FC2
0x180008faf  test    cs:byte_180020581, 4
0x180008fb6  jz      short loc_180008FCA
0x180008fb8  mov     r9d, edx
0x180008fbb  lea     rdx, LiveSsp_TraceFunction_Exit
0x180008fc2  mov     r8, rcx
0x180008fc5  jmp     McTemplateU0sd_EventWriteTransfer
0x180008fca  xor     eax, eax
0x180008fcc  retn
```
