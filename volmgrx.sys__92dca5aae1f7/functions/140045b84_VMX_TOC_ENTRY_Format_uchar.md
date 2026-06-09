# VMX_TOC_ENTRY::Format(uchar * *)

- ea: `0x140045b84`
- end: `0x140045c90`
- name: `?Format@VMX_TOC_ENTRY@@QEAAXPEAPEAE@Z`
- size: `268`
- prototype: `void __fastcall(VMX_TOC_ENTRY *__hidden this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140047eac`

## callees

- `0x1400097c0`
- `0x140045b84`

## string_xrefs

- `0x140045b9a`: `config`

## pseudocode

```c
void __fastcall VMX_TOC_ENTRY::Format(VMX_TOC_ENTRY *this, unsigned __int8 **a2)
{
  char v2; // al
  __int64 v4; // r10
  VMX_TOC_ENTRY *v5; // r11
  const char *v6; // r8

  v2 = *((_BYTE *)this + 32);
  v4 = (__int64)*a2;
  v5 = this;
  if ( v2 == 1 )
  {
    v6 = "config";
LABEL_5:
    RtlStringCbCopyA((NTSTRSAFE_PSTR)v4, 9u, v6);
    goto LABEL_6;
  }
  if ( v2 == 2 )
  {
    v6 = "log";
    goto LABEL_5;
  }
LABEL_6:
  *(_BYTE *)(v4 + 8) = *((_BYTE *)v5 + 35);
  *(_BYTE *)(v4 + 9) = *((_BYTE *)v5 + 34);
  *(_BYTE *)(v4 + 10) = *((_BYTE *)v5 + 47);
  *(_BYTE *)(v4 + 11) = *((_BYTE *)v5 + 46);
  *(_BYTE *)(v4 + 12) = *((_BYTE *)v5 + 45);
  *(_BYTE *)(v4 + 13) = *((_BYTE *)v5 + 44);
  *(_BYTE *)(v4 + 14) = *((_BYTE *)v5 + 43);
  *(_BYTE *)(v4 + 15) = *((_BYTE *)v5 + 42);
  *(_BYTE *)(v4 + 16) = *((_BYTE *)v5 + 41);
  *(_BYTE *)(v4 + 17) = *((_BYTE *)v5 + 40);
  *(_BYTE *)(v4 + 18) = *((_BYTE *)v5 + 55);
  *(_BYTE *)(v4 + 19) = *((_BYTE *)v5 + 54);
  *(_BYTE *)(v4 + 20) = *((_BYTE *)v5 + 53);
  *(_BYTE *)(v4 + 21) = *((_BYTE *)v5 + 52);
  *(_BYTE *)(v4 + 22) = *((_BYTE *)v5 + 51);
  *(_BYTE *)(v4 + 23) = *((_BYTE *)v5 + 50);
  *(_BYTE *)(v4 + 24) = *((_BYTE *)v5 + 49);
  *(_BYTE *)(v4 + 25) = *((_BYTE *)v5 + 48);
  *(_WORD *)(v4 + 26) = 1536;
  *(_BYTE *)(v4 + 28) = *((_BYTE *)v5 + 57);
  *(_BYTE *)(v4 + 29) = *((_BYTE *)v5 + 56);
  *(_BYTE *)(v4 + 30) = *((_BYTE *)v5 + 63);
  *(_BYTE *)(v4 + 31) = *((_BYTE *)v5 + 62);
  *(_BYTE *)(v4 + 32) = *((_BYTE *)v5 + 61);
  *(_BYTE *)(v4 + 33) = *((_BYTE *)v5 + 60);
  *a2 = (unsigned __int8 *)(v4 + 34);
}

```

## disassembly

```asm
0x140045b84  push    rbx
0x140045b86  sub     rsp, 20h
0x140045b8a  mov     al, [rcx+20h]
0x140045b8d  mov     rbx, rdx
0x140045b90  mov     r10, [rdx]
0x140045b93  mov     r11, rcx
0x140045b96  cmp     al, 1
0x140045b98  jnz     short loc_140045BA3
0x140045b9a  lea     r8, aConfig; "config"
0x140045ba1  jmp     short loc_140045BAE
0x140045ba3  cmp     al, 2
0x140045ba5  jnz     short loc_140045BBB
0x140045ba7  lea     r8, aLog; "log"
0x140045bae  mov     edx, 9; cbDest
0x140045bb3  mov     rcx, r10; pszDest
0x140045bb6  call    RtlStringCbCopyA
0x140045bbb  mov     al, [r11+23h]
0x140045bbf  mov     [r10+8], al
0x140045bc3  mov     al, [r11+22h]
0x140045bc7  mov     [r10+9], al
0x140045bcb  mov     al, [r11+2Fh]
0x140045bcf  mov     [r10+0Ah], al
0x140045bd3  mov     al, [r11+2Eh]
0x140045bd7  mov     [r10+0Bh], al
0x140045bdb  mov     al, [r11+2Dh]
0x140045bdf  mov     [r10+0Ch], al
0x140045be3  mov     al, [r11+2Ch]
0x140045be7  mov     [r10+0Dh], al
0x140045beb  mov     al, [r11+2Bh]
0x140045bef  mov     [r10+0Eh], al
0x140045bf3  mov     al, [r11+2Ah]
0x140045bf7  mov     [r10+0Fh], al
0x140045bfb  mov     al, [r11+29h]
0x140045bff  mov     [r10+10h], al
0x140045c03  mov     al, [r11+28h]
0x140045c07  mov     [r10+11h], al
0x140045c0b  mov     al, [r11+37h]
0x140045c0f  mov     [r10+12h], al
0x140045c13  mov     al, [r11+36h]
0x140045c17  mov     [r10+13h], al
0x140045c1b  mov     al, [r11+35h]
0x140045c1f  mov     [r10+14h], al
0x140045c23  mov     al, [r11+34h]
0x140045c27  mov     [r10+15h], al
0x140045c2b  mov     al, [r11+33h]
0x140045c2f  mov     [r10+16h], al
0x140045c33  mov     al, [r11+32h]
0x140045c37  mov     [r10+17h], al
0x140045c3b  mov     al, [r11+31h]
0x140045c3f  mov     [r10+18h], al
0x140045c43  mov     al, [r11+30h]
0x140045c47  mov     [r10+19h], al
0x140045c4b  mov     word ptr [r10+1Ah], 600h
0x140045c52  mov     al, [r11+39h]
0x140045c56  mov     [r10+1Ch], al
0x140045c5a  mov     al, [r11+38h]
0x140045c5e  mov     [r10+1Dh], al
0x140045c62  mov     al, [r11+3Fh]
0x140045c66  mov     [r10+1Eh], al
0x140045c6a  mov     al, [r11+3Eh]
0x140045c6e  mov     [r10+1Fh], al
0x140045c72  mov     al, [r11+3Dh]
0x140045c76  mov     [r10+20h], al
0x140045c7a  mov     al, [r11+3Ch]
0x140045c7e  mov     [r10+21h], al
0x140045c82  lea     rax, [r10+22h]
0x140045c86  mov     [rbx], rax
0x140045c89  add     rsp, 20h
0x140045c8d  pop     rbx
0x140045c8e  retn
```
