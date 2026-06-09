# WString::DeleteString(void)

- ea: `0x18001ce68`
- end: `0x18001cee9`
- name: `?DeleteString@WString@@QEAAXXZ`
- size: `129`
- prototype: `void __fastcall(unsigned __int16 **this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001699c`
- `0x18001d0d4`

## callees

- `0x18001ce68`
- `0x18001cef0`
- `0x18001d128`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001cec5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cec5`

## pseudocode

```c
void __fastcall WString::DeleteString(unsigned __int16 **this)
{
  __int16 v1; // ax
  __int16 v3; // ax

  v1 = *((_WORD *)this + 6);
  if ( (v1 & 0x20) != 0 )
  {
    if ( (v1 & 0x1000) == 0 )
      return;
    if ( *this )
      **this = 0;
    WString::InternalFree((WString *)this, this);
    v3 = -4129;
    goto LABEL_12;
  }
  if ( (v1 & 0x10) != 0 )
  {
    *this = 0;
    *((_WORD *)this + 6) = v1 & 0xFFEF;
    return;
  }
  if ( (v1 & 0x44) != 0 )
  {
    if ( *this )
    {
      SysFreeString(*this);
      *this = 0;
    }
    v3 = -65;
LABEL_12:
    *((_WORD *)this + 6) &= v3;
    return;
  }
  WString::FreeString(this);
}

```

## disassembly

```asm
0x18001ce68  mov     [rsp+arg_0], rbx
0x18001ce6d  push    rdi
0x18001ce6e  sub     rsp, 20h
0x18001ce72  movzx   eax, word ptr [rcx+0Ch]
0x18001ce76  mov     rbx, rcx
0x18001ce79  test    al, 20h
0x18001ce7b  jz      short loc_18001CEA0
0x18001ce7d  bt      ax, 0Ch
0x18001ce82  jnb     short loc_18001CEDE
0x18001ce84  mov     rax, [rcx]
0x18001ce87  xor     edi, edi
0x18001ce89  test    rax, rax
0x18001ce8c  jz      short loc_18001CE91
0x18001ce8e  mov     [rax], di
0x18001ce91  mov     rdx, rbx; unsigned __int16 **
0x18001ce94  call    ?InternalFree@WString@@IEBAXAEAPEAG@Z; WString::InternalFree(ushort * &)
0x18001ce99  mov     eax, 0EFDFh
0x18001ce9e  jmp     short loc_18001CED3
0x18001cea0  test    al, 10h
0x18001cea2  jz      short loc_18001CEB7
0x18001cea4  xor     edi, edi
0x18001cea6  mov     [rcx], rdi
0x18001cea9  mov     ecx, 0FFEFh
0x18001ceae  and     ax, cx
0x18001ceb1  mov     [rbx+0Ch], ax
0x18001ceb5  jmp     short loc_18001CEDE
0x18001ceb7  test    al, 44h
0x18001ceb9  jz      short loc_18001CED9
0x18001cebb  xor     edi, edi
0x18001cebd  cmp     [rcx], rdi
0x18001cec0  jz      short loc_18001CECE
0x18001cec2  mov     rcx, [rcx]; bstrString
0x18001cec5  call    cs:__imp_SysFreeString
0x18001cecb  mov     [rbx], rdi
0x18001cece  mov     eax, 0FFBFh
0x18001ced3  and     [rbx+0Ch], ax
0x18001ced7  jmp     short loc_18001CEDE
0x18001ced9  call    ?FreeString@WString@@SAXAEAPEAG@Z; WString::FreeString(ushort * &)
0x18001cede  mov     rbx, [rsp+28h+arg_0]
0x18001cee3  add     rsp, 20h
0x18001cee7  pop     rdi
0x18001cee8  retn
```
