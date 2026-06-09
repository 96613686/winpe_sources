# MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)

- ea: `0x180008edc`
- end: `0x180008f66`
- name: `?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(MsaTracingInternal *this, const char *, const char *)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180005d3c`
- `0x180006410`
- `0x180007120`
- `0x180007b00`
- `0x18000a134`
- `0x18000a26c`
- `0x18000a3e8`
- `0x18000ab84`
- `0x18000aec0`
- `0x18000b080`
- `0x18000b5b4`
- `0x18000b700`
- `0x18000b820`
- `0x18000b9e0`
- `0x18000bac0`
- `0x18000bbf8`
- `0x18000bc8c`
- `0x18000dc00`

## callees

- `0x180006614`
- `0x180008edc`
- `0x180009a40`

## pseudocode

```c
__int64 __fastcall MsaTracingInternal::TraceFunctionEnter(MsaTracingInternal *this, const char *a2, const char *a3)
{
  char v3; // bl
  int v4; // edi
  unsigned int BaseFileName; // eax
  int v6; // ecx
  const char *v7; // rdx

  v3 = (char)a3;
  v4 = (int)a2;
  if ( dword_180020A0C == 1 )
  {
    if ( (byte_180020581 & 4) != 0 )
    {
      BaseFileName = (unsigned int)MsaTracingInternal::GetBaseFileName(this, a2);
      v7 = (const char *)LiveSsp_TraceFunction_Enter;
      return McTemplateU0ssqz_EventWriteTransfer(v6, (_DWORD)v7, BaseFileName, v4, v3);
    }
  }
  else if ( dword_180020A0C == 2 )
  {
    if ( (byte_180020582 & 4) != 0 )
    {
      BaseFileName = (unsigned int)MsaTracingInternal::GetBaseFileName(this, a2);
      v7 = CredProv_TraceFunction_Enter;
      return McTemplateU0ssqz_EventWriteTransfer(v6, (_DWORD)v7, BaseFileName, v4, v3);
    }
  }
  else if ( dword_180020A0C == 3 && (byte_180020583 & 4) != 0 )
  {
    BaseFileName = (unsigned int)MsaTracingInternal::GetBaseFileName(this, a2);
    v7 = WlidNsp_TraceFunction_Enter;
    return McTemplateU0ssqz_EventWriteTransfer(v6, (_DWORD)v7, BaseFileName, v4, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180008edc  mov     [rsp+arg_0], rbx
0x180008ee1  push    rdi
0x180008ee2  sub     rsp, 30h
0x180008ee6  mov     r9d, cs:dword_180020A0C
0x180008eed  mov     ebx, r8d
0x180008ef0  mov     rdi, rdx
0x180008ef3  sub     r9d, 1
0x180008ef7  jz      short loc_180008F33
0x180008ef9  sub     r9d, 1
0x180008efd  jz      short loc_180008F1C
0x180008eff  cmp     r9d, 1
0x180008f03  jnz     short loc_180008F59
0x180008f05  test    cs:byte_180020583, 4
0x180008f0c  jz      short loc_180008F59
0x180008f0e  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x180008f13  lea     rdx, WlidNsp_TraceFunction_Enter; char *
0x180008f1a  jmp     short loc_180008F48
0x180008f1c  test    cs:byte_180020582, 4
0x180008f23  jz      short loc_180008F59
0x180008f25  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x180008f2a  lea     rdx, CredProv_TraceFunction_Enter; char *
0x180008f31  jmp     short loc_180008F48
0x180008f33  test    cs:byte_180020581, 4
0x180008f3a  jz      short loc_180008F59
0x180008f3c  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x180008f41  lea     rdx, LiveSsp_TraceFunction_Enter
0x180008f48  mov     r9, rdi
0x180008f4b  mov     [rsp+38h+var_18], ebx
0x180008f4f  mov     r8, rax
0x180008f52  call    McTemplateU0ssqz_EventWriteTransfer
0x180008f57  jmp     short loc_180008F5B
0x180008f59  xor     eax, eax
0x180008f5b  mov     rbx, [rsp+38h+arg_0]
0x180008f60  add     rsp, 30h
0x180008f64  pop     rdi
0x180008f65  retn
```
