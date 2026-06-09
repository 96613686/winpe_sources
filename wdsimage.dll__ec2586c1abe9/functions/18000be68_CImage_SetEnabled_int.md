# CImage::SetEnabled(int)

- ea: `0x18000be68`
- end: `0x18000bef1`
- name: `?SetEnabled@CImage@@QEAAJH@Z`
- size: `137`
- prototype: `__int64 __fastcall(CImage *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005e10`
- `0x18000c77c`

## callees

- `0x18000be68`
- `0x18000d6b0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18000be95`
- `KERNEL32!SetFileAttributesW` at `0x18000be95`
- `KERNEL32!GetLastError` at `0x18000bea5`
- `KERNEL32!GetLastError` at `0x18000bea5`

## pseudocode

```c
__int64 __fastcall CImage::SetEnabled(CImage *this, int a2)
{
  int v2; // edi
  const WCHAR *v4; // rcx
  int v5; // eax
  DWORD v6; // edi
  signed int v7; // ebx
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax

  v2 = *((_DWORD *)this + 89);
  v4 = (const WCHAR *)*((_QWORD *)this + 11);
  v5 = v2 | 2;
  v6 = v2 & 0xFFFFFFFD;
  v7 = 0;
  if ( !a2 )
    v6 = v5;
  if ( SetFileAttributesW(v4, v6) )
  {
    *((_DWORD *)this + 89) = v6;
  }
  else
  {
    LastError = GetLastError();
    v11 = ElValidateWin32_4(LastError, v9, v10, 1367);
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000be68  mov     [rsp+arg_0], rbx
0x18000be6d  mov     [rsp+arg_8], rsi
0x18000be72  push    rdi
0x18000be73  sub     rsp, 20h
0x18000be77  mov     edi, [rcx+164h]
0x18000be7d  mov     rsi, rcx
0x18000be80  mov     rcx, [rcx+58h]; lpFileName
0x18000be84  mov     eax, edi
0x18000be86  or      eax, 2
0x18000be89  and     edi, 0FFFFFFFDh
0x18000be8c  xor     ebx, ebx
0x18000be8e  test    edx, edx
0x18000be90  cmovz   edi, eax
0x18000be93  mov     edx, edi; dwFileAttributes
0x18000be95  call    cs:__imp_SetFileAttributesW
0x18000be9c  nop     dword ptr [rax+rax+00h]
0x18000bea1  test    eax, eax
0x18000bea3  jnz     short loc_18000BED8
0x18000bea5  call    cs:__imp_GetLastError
0x18000beac  nop     dword ptr [rax+rax+00h]
0x18000beb1  mov     ecx, eax
0x18000beb3  mov     r9d, 557h
0x18000beb9  call    ElValidateWin32_4
0x18000bebe  mov     ebx, eax
0x18000bec0  test    eax, eax
0x18000bec2  jle     short loc_18000BECD
0x18000bec4  movzx   ebx, ax
0x18000bec7  or      ebx, 80070000h
0x18000becd  test    ebx, ebx
0x18000becf  js      short loc_18000BEDE
0x18000bed1  mov     ebx, 80004005h
0x18000bed6  jmp     short loc_18000BEDE
0x18000bed8  mov     [rsi+164h], edi
0x18000bede  mov     rsi, [rsp+28h+arg_8]
0x18000bee3  mov     eax, ebx
0x18000bee5  mov     rbx, [rsp+28h+arg_0]
0x18000beea  add     rsp, 20h
0x18000beee  pop     rdi
0x18000beef  retn
```
