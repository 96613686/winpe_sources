# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800087e4`
- end: `0x1800088dd`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `249`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d30`
- `0x180008e44`
- `0x1800091fc`

## callees

- `0x1800087e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008834`
- `msvcrt!memcpy_s` at `0x18000886c`
- `msvcrt!memcpy_s` at `0x18000889d`
- `msvcrt!memcpy_s` at `0x180008834`
- `msvcrt!memcpy_s` at `0x18000886c`
- `msvcrt!memcpy_s` at `0x18000889d`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbp
  __int16 v8; // ax
  char *v9; // rbp
  unsigned __int8 *v10; // rcx
  bool result; // al
  unsigned __int16 v12; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v12 = 0;
    memcpy_s(&v12, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v12;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    memcpy_s((char *)this + 4, 4u, v5, 4u);
  }
  v5 = v7;
LABEL_8:
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_11;
  v9 = v5 + 2;
  if ( v5 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v5, 2u);
  v5 = v9;
LABEL_11:
  v10 = (unsigned __int8 *)&v5[*((unsigned __int16 *)this + 4)];
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v5;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x1800087e4  mov     rax, rsp
0x1800087e7  mov     [rax+10h], rbx
0x1800087eb  mov     [rax+18h], rbp
0x1800087ef  push    rsi
0x1800087f0  push    rdi
0x1800087f1  push    r12
0x1800087f3  push    r14
0x1800087f5  push    r15
0x1800087f7  sub     rsp, 20h
0x1800087fb  xor     r12d, r12d
0x1800087fe  mov     rdi, r8
0x180008801  cmp     byte ptr [rcx+2], 1
0x180008805  mov     r15, rdx
0x180008808  mov     r8, [rdx]; Source
0x18000880b  mov     rbx, rcx
0x18000880e  jnz     short loc_18000884A
0x180008810  lea     rbp, [r8+2]
0x180008814  cmp     rbp, rdi
0x180008817  ja      loc_1800088B8
0x18000881d  lea     esi, [r12+2]
0x180008822  mov     [rcx+10h], r8
0x180008826  mov     r9d, esi; SourceSize
0x180008829  mov     [rax+8], r12w
0x18000882e  mov     edx, esi; DestinationSize
0x180008830  lea     rcx, [rax+8]; Destination
0x180008834  call    cs:__imp_memcpy_s
0x18000883b  nop     dword ptr [rax+rax+00h]
0x180008840  movzx   eax, [rsp+48h+arg_0]
0x180008845  mov     [rbx+4], eax
0x180008848  jmp     short loc_180008878
0x18000884a  mov     esi, 2
0x18000884f  cmp     [rcx+2], sil
0x180008853  jnz     short loc_18000887B
0x180008855  lea     rbp, [r8+4]
0x180008859  cmp     rbp, rdi
0x18000885c  ja      short loc_1800088B8
0x18000885e  lea     edx, [rsi+2]; DestinationSize
0x180008861  mov     [rcx+10h], r8
0x180008865  mov     r9d, edx; SourceSize
0x180008868  add     rcx, 4; Destination
0x18000886c  call    cs:__imp_memcpy_s
0x180008873  nop     dword ptr [rax+rax+00h]
0x180008878  mov     r8, rbp; Source
0x18000887b  movzx   eax, word ptr [rbx]
0x18000887e  lea     r14, [rbx+8]
0x180008882  mov     [r14], ax
0x180008886  test    ax, ax
0x180008889  jnz     short loc_1800088AC
0x18000888b  lea     rbp, [r8+2]
0x18000888f  cmp     rbp, rdi
0x180008892  ja      short loc_1800088B8
0x180008894  mov     r9, rsi; SourceSize
0x180008897  mov     rdx, rsi; DestinationSize
0x18000889a  mov     rcx, r14; Destination
0x18000889d  call    cs:__imp_memcpy_s
0x1800088a4  nop     dword ptr [rax+rax+00h]
0x1800088a9  mov     r8, rbp
0x1800088ac  movzx   ecx, word ptr [r14]
0x1800088b0  add     rcx, r8
0x1800088b3  cmp     rcx, rdi
0x1800088b6  jbe     short loc_1800088BC
0x1800088b8  xor     al, al
0x1800088ba  jmp     short loc_1800088C5
0x1800088bc  mov     [rbx+18h], r8
0x1800088c0  mov     al, 1
0x1800088c2  mov     [r15], rcx
0x1800088c5  mov     rbx, [rsp+48h+arg_8]
0x1800088ca  mov     rbp, [rsp+48h+arg_10]
0x1800088cf  add     rsp, 20h
0x1800088d3  pop     r15
0x1800088d5  pop     r14
0x1800088d7  pop     r12
0x1800088d9  pop     rdi
0x1800088da  pop     rsi
0x1800088db  retn
```
