# CWSHRemote::CError::get_Source(ushort * *)

- ea: `0x140001b40`
- end: `0x140001bc8`
- name: `?get_Source@CError@CWSHRemote@@UEAAJPEAPEAG@Z`
- size: `136`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000169c`
- `0x140001864`
- `0x140001b40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001b99`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140001b99`
- `OLEAUT32!__imp_SysStringLen` at `0x140001b8d`
- `OLEAUT32!__imp_SysStringLen` at `0x140001b8d`
- `KERNEL32!GetCurrentThreadId` at `0x140001b6b`
- `KERNEL32!GetCurrentThreadId` at `0x140001b6b`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_Source(CWSHRemote::CError *this, unsigned __int16 **a2)
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
    v6 = SysStringLen(*((BSTR *)this + 5));
    *a2 = SysAllocStringLen(*((const OLECHAR **)this + 5), v6);
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
0x140001b40  mov     [rsp+arg_0], rbx
0x140001b45  mov     [rsp+arg_8], rsi
0x140001b4a  push    rdi
0x140001b4b  sub     rsp, 20h
0x140001b4f  mov     rdi, rdx
0x140001b52  mov     rsi, rcx
0x140001b55  test    rdx, rdx
0x140001b58  jnz     short loc_140001B61
0x140001b5a  mov     eax, 80004003h
0x140001b5f  jmp     short loc_140001BB8
0x140001b61  mov     qword ptr [rdx], 0
0x140001b68  mov     ebx, [rcx+0Ch]
0x140001b6b  call    cs:__imp_GetCurrentThreadId
0x140001b71  cmp     eax, ebx
0x140001b73  jz      short loc_140001B7C
0x140001b75  mov     eax, 8000FFFFh
0x140001b7a  jmp     short loc_140001BB8
0x140001b7c  lea     rcx, [rsi+48h]; this
0x140001b80  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140001b85  test    eax, eax
0x140001b87  jz      short loc_140001BAB
0x140001b89  mov     rcx, [rsi+28h]; pbstr
0x140001b8d  call    cs:__imp_SysStringLen
0x140001b93  mov     rcx, [rsi+28h]; strIn
0x140001b97  mov     edx, eax; ui
0x140001b99  call    cs:__imp_SysAllocStringLen
0x140001b9f  lea     rcx, [rsi+48h]; this
0x140001ba3  mov     [rdi], rax
0x140001ba6  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140001bab  xor     eax, eax
0x140001bad  mov     ecx, 8007000Eh
0x140001bb2  cmp     [rdi], rax
0x140001bb5  cmovz   eax, ecx
0x140001bb8  mov     rbx, [rsp+28h+arg_0]
0x140001bbd  mov     rsi, [rsp+28h+arg_8]
0x140001bc2  add     rsp, 20h
0x140001bc6  pop     rdi
0x140001bc7  retn
```
