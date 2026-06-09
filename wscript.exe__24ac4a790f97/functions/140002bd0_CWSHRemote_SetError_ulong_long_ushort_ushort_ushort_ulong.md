# CWSHRemote::SetError(ulong,long,ushort *,ushort *,ushort *,ulong)

- ea: `0x140002bd0`
- end: `0x140002cbb`
- name: `?SetError@CWSHRemote@@QEAAJKJPEAG00K@Z`
- size: `235`
- prototype: `int(CWSHRemote *__hidden this, unsigned int, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140005990`
- `0x140005ab0`
- `0x140005bc0`

## callees

- `0x14000169c`
- `0x140001864`
- `0x140002bd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002bf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002c4c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002c72`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002bf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002c4c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002c72`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c0b`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c14`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c1c`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c0b`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c14`
- `OLEAUT32!__imp_SysFreeString` at `0x140002c1c`
- `OLEAUT32!__imp_SysStringLen` at `0x140002bed`
- `OLEAUT32!__imp_SysStringLen` at `0x140002c3c`
- `OLEAUT32!__imp_SysStringLen` at `0x140002c62`
- `OLEAUT32!__imp_SysStringLen` at `0x140002bed`
- `OLEAUT32!__imp_SysStringLen` at `0x140002c3c`
- `OLEAUT32!__imp_SysStringLen` at `0x140002c62`

## pseudocode

```c
__int64 __fastcall CWSHRemote::SetError(
        CWSHRemote *this,
        __int32 a2,
        __int32 a3,
        unsigned __int16 *a4,
        unsigned __int16 *pbstr,
        unsigned __int16 *strIn,
        unsigned int a7)
{
  __int64 v7; // rdi
  UINT v11; // eax
  OLECHAR *v12; // rsi
  OLECHAR *v13; // rbx
  UINT v15; // eax
  UINT v16; // eax
  BSTR v17; // rbp

  v7 = *((_QWORD *)this + 8);
  v11 = SysStringLen(a4);
  v12 = SysAllocStringLen(a4, v11);
  if ( !v12 )
  {
    v13 = 0;
LABEL_3:
    SysFreeString(v12);
    SysFreeString(v13);
    SysFreeString(0);
    return 2147942414LL;
  }
  v15 = SysStringLen(pbstr);
  v13 = SysAllocStringLen(pbstr, v15);
  if ( !v13 )
    goto LABEL_3;
  v16 = SysStringLen(strIn);
  v17 = SysAllocStringLen(strIn, v16);
  if ( !v17 )
    goto LABEL_3;
  _InterlockedExchange((volatile __int32 *)(v7 + 20), a7);
  _InterlockedExchange((volatile __int32 *)(v7 + 16), a2);
  _InterlockedExchange((volatile __int32 *)(v7 + 24), a3);
  if ( (unsigned int)CCriticalSection::Enter((CCriticalSection *)(v7 + 72)) )
  {
    *(_QWORD *)(v7 + 32) = v13;
    *(_QWORD *)(v7 + 40) = v12;
    *(_QWORD *)(v7 + 48) = v17;
    CCriticalSection::Leave((struct _RTL_CRITICAL_SECTION *)(v7 + 72));
  }
  return 0;
}

```

## disassembly

```asm
0x140002bd0  push    rbx
0x140002bd2  push    rbp
0x140002bd3  push    rsi
0x140002bd4  push    rdi
0x140002bd5  push    r14
0x140002bd7  push    r15
0x140002bd9  sub     rsp, 28h
0x140002bdd  mov     rdi, [rcx+40h]
0x140002be1  mov     rbx, r9
0x140002be4  mov     rcx, r9; pbstr
0x140002be7  mov     r14d, r8d
0x140002bea  mov     r15d, edx
0x140002bed  call    cs:__imp_SysStringLen
0x140002bf3  mov     edx, eax; ui
0x140002bf5  mov     rcx, rbx; strIn
0x140002bf8  call    cs:__imp_SysAllocStringLen
0x140002bfe  mov     rsi, rax
0x140002c01  test    rax, rax
0x140002c04  jnz     short loc_140002C34
0x140002c06  xor     ebx, ebx
0x140002c08  mov     rcx, rsi; bstrString
0x140002c0b  call    cs:__imp_SysFreeString
0x140002c11  mov     rcx, rbx; bstrString
0x140002c14  call    cs:__imp_SysFreeString
0x140002c1a  xor     ecx, ecx; bstrString
0x140002c1c  call    cs:__imp_SysFreeString
0x140002c22  mov     eax, 8007000Eh
0x140002c27  add     rsp, 28h
0x140002c2b  pop     r15
0x140002c2d  pop     r14
0x140002c2f  pop     rdi
0x140002c30  pop     rsi
0x140002c31  pop     rbp
0x140002c32  pop     rbx
0x140002c33  retn
0x140002c34  mov     rcx, [rsp+58h+pbstr]; pbstr
0x140002c3c  call    cs:__imp_SysStringLen
0x140002c42  mov     rcx, [rsp+58h+pbstr]; strIn
0x140002c4a  mov     edx, eax; ui
0x140002c4c  call    cs:__imp_SysAllocStringLen
0x140002c52  mov     rbx, rax
0x140002c55  test    rax, rax
0x140002c58  jz      short loc_140002C08
0x140002c5a  mov     rcx, [rsp+58h+strIn]; pbstr
0x140002c62  call    cs:__imp_SysStringLen
0x140002c68  mov     rcx, [rsp+58h+strIn]; strIn
0x140002c70  mov     edx, eax; ui
0x140002c72  call    cs:__imp_SysAllocStringLen
0x140002c78  mov     rbp, rax
0x140002c7b  test    rax, rax
0x140002c7e  jz      short loc_140002C08
0x140002c80  mov     ecx, [rsp+58h+arg_30]
0x140002c87  xchg    ecx, [rdi+14h]
0x140002c8a  xchg    r15d, [rdi+10h]
0x140002c8e  xchg    r14d, [rdi+18h]
0x140002c92  lea     rcx, [rdi+48h]; this
0x140002c96  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140002c9b  test    eax, eax
0x140002c9d  jz      short loc_140002CB4
0x140002c9f  lea     rcx, [rdi+48h]; this
0x140002ca3  mov     [rdi+20h], rbx
0x140002ca7  mov     [rdi+28h], rsi
0x140002cab  mov     [rdi+30h], rbp
0x140002caf  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140002cb4  xor     eax, eax
0x140002cb6  jmp     loc_140002C27
```
