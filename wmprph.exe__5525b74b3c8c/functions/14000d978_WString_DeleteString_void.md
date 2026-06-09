# WString::DeleteString(void)

- ea: `0x14000d978`
- end: `0x14000d9f9`
- name: `?DeleteString@WString@@QEAAXXZ`
- size: `129`
- prototype: `void __fastcall(unsigned __int16 **this)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x140002190`
- `0x140002370`
- `0x140003c20`
- `0x140004784`
- `0x140004e20`
- `0x140005c60`
- `0x140008cf0`
- `0x14000da00`
- `0x14000dcf8`
- `0x14000de4c`
- `0x14000dee0`

## callees

- `0x14000d978`
- `0x14000db3c`
- `0x14000dea0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000d9d5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d9d5`

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
0x14000d978  mov     [rsp+arg_0], rbx
0x14000d97d  push    rdi
0x14000d97e  sub     rsp, 20h
0x14000d982  movzx   eax, word ptr [rcx+0Ch]
0x14000d986  mov     rbx, rcx
0x14000d989  test    al, 20h
0x14000d98b  jz      short loc_14000D9B0
0x14000d98d  bt      ax, 0Ch
0x14000d992  jnb     short loc_14000D9EE
0x14000d994  mov     rax, [rcx]
0x14000d997  xor     edi, edi
0x14000d999  test    rax, rax
0x14000d99c  jz      short loc_14000D9A1
0x14000d99e  mov     [rax], di
0x14000d9a1  mov     rdx, rbx; unsigned __int16 **
0x14000d9a4  call    ?InternalFree@WString@@IEBAXAEAPEAG@Z; WString::InternalFree(ushort * &)
0x14000d9a9  mov     eax, 0EFDFh
0x14000d9ae  jmp     short loc_14000D9E3
0x14000d9b0  test    al, 10h
0x14000d9b2  jz      short loc_14000D9C7
0x14000d9b4  xor     edi, edi
0x14000d9b6  mov     [rcx], rdi
0x14000d9b9  mov     ecx, 0FFEFh
0x14000d9be  and     ax, cx
0x14000d9c1  mov     [rbx+0Ch], ax
0x14000d9c5  jmp     short loc_14000D9EE
0x14000d9c7  test    al, 44h
0x14000d9c9  jz      short loc_14000D9E9
0x14000d9cb  xor     edi, edi
0x14000d9cd  cmp     [rcx], rdi
0x14000d9d0  jz      short loc_14000D9DE
0x14000d9d2  mov     rcx, [rcx]; bstrString
0x14000d9d5  call    cs:__imp_SysFreeString
0x14000d9db  mov     [rbx], rdi
0x14000d9de  mov     eax, 0FFBFh
0x14000d9e3  and     [rbx+0Ch], ax
0x14000d9e7  jmp     short loc_14000D9EE
0x14000d9e9  call    ?FreeString@WString@@SAXAEAPEAG@Z; WString::FreeString(ushort * &)
0x14000d9ee  mov     rbx, [rsp+28h+arg_0]
0x14000d9f3  add     rsp, 20h
0x14000d9f7  pop     rdi
0x14000d9f8  retn
```
