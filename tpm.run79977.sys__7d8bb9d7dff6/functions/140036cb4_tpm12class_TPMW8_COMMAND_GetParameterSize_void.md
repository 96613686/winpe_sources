# tpm12class::TPMW8_COMMAND::GetParameterSize(void)

- ea: `0x140036cb4`
- end: `0x140036d51`
- name: `?GetParameterSize@TPMW8_COMMAND@tpm12class@@QEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140038880`
- `0x140038ea0`

## callees

- `0x14000cc3c`
- `0x140036188`
- `0x140036cb4`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::GetParameterSize(tpm12class::TPMW8_COMMAND *this)
{
  int Data; // ecx
  int v3; // eax
  struct tpm12class::TPMW8_SESSION *v4; // rdx

  *((_BYTE *)this + 48) = 1;
  Data = tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 19);
  if ( Data >= 0 )
  {
    v3 = *((_DWORD *)this + 6);
    *((_BYTE *)this + 48) = 0;
    *((_DWORD *)this + 18) = v3;
    if ( this == (tpm12class::TPMW8_COMMAND *)-80LL )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      *((_DWORD *)this + 20) = *((_DWORD *)this + 10);
      Data = 0;
      if ( *((_WORD *)this + 29) == 0x8002
        && ((v4 = (struct tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21)) != 0 && (*((_BYTE *)v4 + 764) & 0x40) != 0
         || (v4 = (struct tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 22)) != 0 && (*((_BYTE *)v4 + 764) & 0x40) != 0
         || (v4 = (struct tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 23)) != 0 && (*((_BYTE *)v4 + 764) & 0x40) != 0) )
      {
        return (unsigned int)tpm12class::TPMW8_COMMAND::DecryptFirstRspParameter(this, v4);
      }
    }
  }
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x140036cb4  push    rbx
0x140036cb6  sub     rsp, 20h
0x140036cba  lea     rdx, [rcx+4Ch]; unsigned int *
0x140036cbe  mov     byte ptr [rcx+30h], 1
0x140036cc2  mov     rbx, rcx
0x140036cc5  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x140036cca  mov     ecx, eax
0x140036ccc  test    eax, eax
0x140036cce  js      short loc_140036D48
0x140036cd0  mov     eax, [rbx+18h]
0x140036cd3  lea     rcx, [rbx+50h]
0x140036cd7  mov     byte ptr [rbx+30h], 0
0x140036cdb  mov     [rbx+48h], eax
0x140036cde  test    rcx, rcx
0x140036ce1  jnz     short loc_140036CEA
0x140036ce3  mov     ecx, 80070057h
0x140036ce8  jmp     short loc_140036D48
0x140036cea  mov     eax, [rbx+28h]
0x140036ced  mov     [rcx], eax
0x140036cef  xor     ecx, ecx
0x140036cf1  mov     eax, 8002h
0x140036cf6  cmp     [rbx+3Ah], ax
0x140036cfa  jnz     short loc_140036D48
0x140036cfc  mov     rdx, [rbx+0A8h]
0x140036d03  mov     r8b, 40h ; '@'
0x140036d06  test    rdx, rdx
0x140036d09  jz      short loc_140036D14
0x140036d0b  test    [rdx+2FCh], r8b
0x140036d12  jnz     short loc_140036D3E
0x140036d14  mov     rdx, [rbx+0B0h]
0x140036d1b  test    rdx, rdx
0x140036d1e  jz      short loc_140036D29
0x140036d20  test    [rdx+2FCh], r8b
0x140036d27  jnz     short loc_140036D3E
0x140036d29  mov     rdx, [rbx+0B8h]; struct tpm12class::TPMW8_SESSION *
0x140036d30  test    rdx, rdx
0x140036d33  jz      short loc_140036D48
0x140036d35  test    [rdx+2FCh], r8b
0x140036d3c  jz      short loc_140036D48
0x140036d3e  mov     rcx, rbx; this
0x140036d41  call    ?DecryptFirstRspParameter@TPMW8_COMMAND@tpm12class@@IEAAJPEAVTPMW8_SESSION@2@@Z; tpm12class::TPMW8_COMMAND::DecryptFirstRspParameter(tpm12class::TPMW8_SESSION *)
0x140036d46  mov     ecx, eax
0x140036d48  mov     eax, ecx
0x140036d4a  add     rsp, 20h
0x140036d4e  pop     rbx
0x140036d4f  retn
```
