# CWSHRemote::CError::get_SourceText(ushort * *)

- ea: `0x140001bd0`
- end: `0x140001c58`
- name: `?get_SourceText@CError@CWSHRemote@@UEAAJPEAPEAG@Z`
- size: `136`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000169c`
- `0x140001864`
- `0x140001bd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001c29`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001c29`
- `OLEAUT32!__imp_SysStringLen` at `0x140001c1d`
- `OLEAUT32!__imp_SysStringLen` at `0x140001c1d`
- `KERNEL32!GetCurrentThreadId` at `0x140001bfb`
- `KERNEL32!GetCurrentThreadId` at `0x140001bfb`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_SourceText(CWSHRemote::CError *this, unsigned __int16 **a2)
{
  __int64 result; // rax
  int v5; // ebx
  UINT v6; // eax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  if ( (unsigned int)CCriticalSection::Enter((CWSHRemote::CError *)((char *)this + 72)) )
  {
    v6 = SysStringLen(*((BSTR *)this + 6));
    *a2 = SysAllocStringLen(*((const OLECHAR **)this + 6), v6);
    CCriticalSection::Leave((CWSHRemote::CError *)((char *)this + 72));
  }
  result = 0;
  if ( !*a2 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x140001bd0  mov     [rsp+arg_0], rbx
0x140001bd5  mov     [rsp+arg_8], rsi
0x140001bda  push    rdi
0x140001bdb  sub     rsp, 20h
0x140001bdf  mov     rdi, rdx
0x140001be2  mov     rsi, rcx
0x140001be5  test    rdx, rdx
0x140001be8  jnz     short loc_140001BF1
0x140001bea  mov     eax, 80004003h
0x140001bef  jmp     short loc_140001C48
0x140001bf1  mov     qword ptr [rdx], 0
0x140001bf8  mov     ebx, [rcx+0Ch]
0x140001bfb  call    cs:__imp_GetCurrentThreadId
0x140001c01  cmp     eax, ebx
0x140001c03  jz      short loc_140001C0C
0x140001c05  mov     eax, 8000FFFFh
0x140001c0a  jmp     short loc_140001C48
0x140001c0c  lea     rcx, [rsi+48h]; this
0x140001c10  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140001c15  test    eax, eax
0x140001c17  jz      short loc_140001C3B
0x140001c19  mov     rcx, [rsi+30h]; pbstr
0x140001c1d  call    cs:__imp_SysStringLen
0x140001c23  mov     rcx, [rsi+30h]; strIn
0x140001c27  mov     edx, eax; ui
0x140001c29  call    cs:__imp_SysAllocStringLen
0x140001c2f  lea     rcx, [rsi+48h]; this
0x140001c33  mov     [rdi], rax
0x140001c36  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140001c3b  xor     eax, eax
0x140001c3d  mov     ecx, 8007000Eh
0x140001c42  cmp     [rdi], rax
0x140001c45  cmovz   eax, ecx
0x140001c48  mov     rbx, [rsp+28h+arg_0]
0x140001c4d  mov     rsi, [rsp+28h+arg_8]
0x140001c52  add     rsp, 20h
0x140001c56  pop     rdi
0x140001c57  retn
```
