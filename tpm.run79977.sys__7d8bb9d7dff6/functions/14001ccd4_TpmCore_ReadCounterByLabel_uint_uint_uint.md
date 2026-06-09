# TpmCore::ReadCounterByLabel(uint,uint *,uint *)

- ea: `0x14001ccd4`
- end: `0x14001ce18`
- name: `?ReadCounterByLabel@TpmCore@@QEAAJIPEAI0@Z`
- size: `324`
- prototype: `__int64 __fastcall(TpmCore *__hidden this, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002173c`

## callees

- `0x140019a94`
- `0x14001a8d4`
- `0x14001ccd4`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmCore::ReadCounterByLabel(TpmCore *this, __int64 a2, unsigned int *a3, unsigned int *a4)
{
  int v4; // ebx

  if ( a4 )
  {
    v4 = TpmCore::Execute(this, 0x65u, "u32u32u32pu32pu16pau32");
    if ( v4 >= 0 )
      return (unsigned int)-1073741275;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001ccd4  mov     [rsp-28h+arg_0], rbx
0x14001ccd9  mov     [rsp-28h+arg_10], rsi
0x14001ccde  mov     [rsp-28h+arg_8], edx
0x14001cce2  push    rbp
0x14001cce3  push    rdi
0x14001cce4  push    r12
0x14001cce6  push    r14
0x14001cce8  push    r15
0x14001ccea  mov     rbp, rsp
0x14001cced  sub     rsp, 60h
0x14001ccf1  xor     eax, eax
0x14001ccf3  mov     [rbp+var_C], 0
0x14001ccfa  mov     word ptr [rbp+arg_8], ax
0x14001ccfe  mov     r14, r9
0x14001cd01  mov     [rbp+var_8], rax
0x14001cd05  mov     rsi, r8
0x14001cd08  mov     r15, rcx
0x14001cd0b  test    r9, r9
0x14001cd0e  jnz     short loc_14001CD1A
0x14001cd10  mov     ebx, 0C000000Dh
0x14001cd15  jmp     loc_14001CDFC
0x14001cd1a  lea     rax, [rbp+var_8]
0x14001cd1e  mov     r9d, 14h
0x14001cd24  mov     [rsp+60h+var_20], rax
0x14001cd29  lea     r8, aU32u32u32pu32p_3; "u32u32u32pu32pu16pau32"
0x14001cd30  lea     rax, [rbp+arg_8]
0x14001cd34  mov     [rsp+60h+var_28], rax
0x14001cd39  lea     rax, [rbp+var_C]
0x14001cd3d  mov     [rsp+60h+var_30], rax
0x14001cd42  lea     edx, [r9+51h]; unsigned int
0x14001cd46  mov     dword ptr [rsp+60h+var_38], 6
0x14001cd4e  mov     [rsp+60h+var_40], 4
0x14001cd57  call    ?Execute@TpmCore@@QEAAJIPEBDZZ; TpmCore::Execute(uint,char const *,...)
0x14001cd5c  mov     ebx, eax
0x14001cd5e  test    eax, eax
0x14001cd60  js      loc_14001CDEE
0x14001cd66  xor     edi, edi
0x14001cd68  movzx   eax, word ptr [rbp+arg_8]
0x14001cd6c  cmp     edi, eax
0x14001cd6e  jnb     short loc_14001CDE9
0x14001cd70  lea     rax, [rbp+var_10]
0x14001cd74  mov     [rbp+arg_18], 0
0x14001cd7b  mov     [rsp+60h+var_28], rax
0x14001cd80  lea     r9, aU32pu16pu32pu3; "u32pu16pu32pu32"
0x14001cd87  lea     rax, [rbp+arg_18]
0x14001cd8b  mov     [rbp+var_10], 0
0x14001cd92  mov     [rsp+60h+var_30], rax
0x14001cd97  lea     rdx, ?IsTpmDisabledStatus@TpmCore@@SA_NJ@Z; bool (*)(int)
0x14001cd9e  mov     rax, [rbp+var_8]
0x14001cda2  mov     r8d, 0DEh; unsigned int
0x14001cda8  mov     [rsp+60h+var_38], 0
0x14001cdb1  mov     ecx, [rax+rdi*4]
0x14001cdb4  mov     dword ptr [rsp+60h+var_40], ecx
0x14001cdb8  mov     rcx, r15; this
0x14001cdbb  call    ?Execute@TpmCore@@QEAAJP6A_NJ@ZIPEBDZZ; TpmCore::Execute(bool (*)(long),uint,char const *,...)
0x14001cdc0  mov     ebx, eax
0x14001cdc2  test    eax, eax
0x14001cdc4  js      short loc_14001CDEE
0x14001cdc6  cmp     [rbp+arg_18], 10001h
0x14001cdcd  jz      short loc_14001CDD3
0x14001cdcf  inc     edi
0x14001cdd1  jmp     short loc_14001CD68
0x14001cdd3  mov     rcx, [rbp+var_8]
0x14001cdd7  test    rsi, rsi
0x14001cdda  jz      short loc_14001CDE1
0x14001cddc  mov     eax, [rcx+rdi*4]
0x14001cddf  mov     [rsi], eax
0x14001cde1  mov     eax, [rbp+var_10]
0x14001cde4  mov     [r14], eax
0x14001cde7  jmp     short loc_14001CDF2
0x14001cde9  mov     ebx, 0C0000225h
0x14001cdee  mov     rcx, [rbp+var_8]; void *
0x14001cdf2  test    rcx, rcx
0x14001cdf5  jz      short loc_14001CDFC
0x14001cdf7  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14001cdfc  lea     r11, [rsp+60h+var_s0]
0x14001ce01  mov     eax, ebx
0x14001ce03  mov     rbx, [r11+30h]
0x14001ce07  mov     rsi, [r11+40h]
0x14001ce0b  mov     rsp, r11
0x14001ce0e  pop     r15
0x14001ce10  pop     r14
0x14001ce12  pop     r12
0x14001ce14  pop     rdi
0x14001ce15  pop     rbp
0x14001ce16  retn
```
