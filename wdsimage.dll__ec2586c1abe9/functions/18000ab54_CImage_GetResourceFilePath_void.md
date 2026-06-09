# CImage::GetResourceFilePath(void)

- ea: `0x18000ab54`
- end: `0x18000abda`
- name: `?GetResourceFilePath@CImage@@QEAAPEAGXZ`
- size: `134`
- prototype: `unsigned __int16 *__fastcall(CImage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800051c0`

## callees

- `0x18000ab54`

## import_xrefs

- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000ab93`
- `WdsCommonLib!WdsIsValidFileExtension` at `0x18000ab93`

## pseudocode

```c
unsigned __int16 *__fastcall CImage::GetResourceFilePath(CImage *this)
{
  unsigned __int16 *result; // rax
  __int64 v3; // rdi
  int v4; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  v4 = 0;
  if ( *((_DWORD *)this + 7) == 2 )
  {
    v3 = 0;
    if ( !*((_DWORD *)this + 91) )
      return (unsigned __int16 *)*((_QWORD *)this + 11);
    while ( (unsigned int)WdsIsValidFileExtension(*(_QWORD *)(*((_QWORD *)this + 46) + 8 * v3), L"RWM", &v4) || !v4 )
    {
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= *((_DWORD *)this + 91) )
        return (unsigned __int16 *)*((_QWORD *)this + 11);
    }
    result = *(unsigned __int16 **)(*((_QWORD *)this + 46) + 8 * v3);
    if ( !result )
      return (unsigned __int16 *)*((_QWORD *)this + 11);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab54  mov     [rsp+arg_8], rbx
0x18000ab59  mov     [rsp+arg_10], rsi
0x18000ab5e  push    rdi
0x18000ab5f  sub     rsp, 20h
0x18000ab63  xor     eax, eax
0x18000ab65  mov     rbx, rcx
0x18000ab68  and     [rsp+28h+arg_0], eax
0x18000ab6c  cmp     dword ptr [rcx+1Ch], 2
0x18000ab70  jnz     short loc_18000ABC9
0x18000ab72  xor     edi, edi
0x18000ab74  cmp     [rcx+16Ch], eax
0x18000ab7a  jbe     short loc_18000ABC5
0x18000ab7c  mov     rcx, [rbx+170h]
0x18000ab83  lea     r8, [rsp+28h+arg_0]
0x18000ab88  lea     rdx, aRwm; "RWM"
0x18000ab8f  mov     rcx, [rcx+rdi*8]
0x18000ab93  call    cs:__imp_WdsIsValidFileExtension
0x18000ab9a  nop     dword ptr [rax+rax+00h]
0x18000ab9f  test    eax, eax
0x18000aba1  jnz     short loc_18000ABA9
0x18000aba3  cmp     [rsp+28h+arg_0], eax
0x18000aba7  jnz     short loc_18000ABB5
0x18000aba9  inc     edi
0x18000abab  cmp     edi, [rbx+16Ch]
0x18000abb1  jb      short loc_18000AB7C
0x18000abb3  jmp     short loc_18000ABC5
0x18000abb5  mov     rax, [rbx+170h]
0x18000abbc  mov     rax, [rax+rdi*8]
0x18000abc0  test    rax, rax
0x18000abc3  jnz     short loc_18000ABC9
0x18000abc5  mov     rax, [rbx+58h]
0x18000abc9  mov     rbx, [rsp+28h+arg_8]
0x18000abce  mov     rsi, [rsp+28h+arg_10]
0x18000abd3  add     rsp, 20h
0x18000abd7  pop     rdi
0x18000abd8  retn
```
