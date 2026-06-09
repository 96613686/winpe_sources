# CWSHRemote::CError::get_Description(ushort * *)

- ea: `0x1400019f0`
- end: `0x140001a78`
- name: `?get_Description@CError@CWSHRemote@@UEAAJPEAPEAG@Z`
- size: `136`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000169c`
- `0x140001864`
- `0x1400019f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001a49`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001a49`
- `OLEAUT32!__imp_SysStringLen` at `0x140001a3d`
- `OLEAUT32!__imp_SysStringLen` at `0x140001a3d`
- `KERNEL32!GetCurrentThreadId` at `0x140001a1b`
- `KERNEL32!GetCurrentThreadId` at `0x140001a1b`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_Description(CWSHRemote::CError *this, unsigned __int16 **a2)
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
    v6 = SysStringLen(*((BSTR *)this + 4));
    *a2 = SysAllocStringLen(*((const OLECHAR **)this + 4), v6);
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
0x1400019f0  mov     [rsp+arg_0], rbx
0x1400019f5  mov     [rsp+arg_8], rsi
0x1400019fa  push    rdi
0x1400019fb  sub     rsp, 20h
0x1400019ff  mov     rdi, rdx
0x140001a02  mov     rsi, rcx
0x140001a05  test    rdx, rdx
0x140001a08  jnz     short loc_140001A11
0x140001a0a  mov     eax, 80004003h
0x140001a0f  jmp     short loc_140001A68
0x140001a11  mov     qword ptr [rdx], 0
0x140001a18  mov     ebx, [rcx+0Ch]
0x140001a1b  call    cs:__imp_GetCurrentThreadId
0x140001a21  cmp     eax, ebx
0x140001a23  jz      short loc_140001A2C
0x140001a25  mov     eax, 8000FFFFh
0x140001a2a  jmp     short loc_140001A68
0x140001a2c  lea     rcx, [rsi+48h]; this
0x140001a30  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140001a35  test    eax, eax
0x140001a37  jz      short loc_140001A5B
0x140001a39  mov     rcx, [rsi+20h]; pbstr
0x140001a3d  call    cs:__imp_SysStringLen
0x140001a43  mov     rcx, [rsi+20h]; strIn
0x140001a47  mov     edx, eax; ui
0x140001a49  call    cs:__imp_SysAllocStringLen
0x140001a4f  lea     rcx, [rsi+48h]; this
0x140001a53  mov     [rdi], rax
0x140001a56  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140001a5b  xor     eax, eax
0x140001a5d  mov     ecx, 8007000Eh
0x140001a62  cmp     [rdi], rax
0x140001a65  cmovz   eax, ecx
0x140001a68  mov     rbx, [rsp+28h+arg_0]
0x140001a6d  mov     rsi, [rsp+28h+arg_8]
0x140001a72  add     rsp, 20h
0x140001a76  pop     rdi
0x140001a77  retn
```
