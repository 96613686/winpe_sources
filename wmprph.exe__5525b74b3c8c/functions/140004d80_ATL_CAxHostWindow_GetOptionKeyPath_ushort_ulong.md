# ATL::CAxHostWindow::GetOptionKeyPath(ushort * *,ulong)

- ea: `0x140004d80`
- end: `0x140004e0f`
- name: `?GetOptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAPEAGK@Z`
- size: `143`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004d80`
- `0x14000f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140004df1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140004df1`
- `OLEAUT32!__imp_SysStringLen` at `0x140004de2`
- `OLEAUT32!__imp_SysStringLen` at `0x140004de2`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetOptionKeyPath(ATL::CAxHostWindow *this, unsigned __int16 **a2)
{
  __int64 v5; // rcx
  int v6; // ecx
  UINT v7; // eax
  unsigned __int16 *v8; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 136LL))(v5);
    if ( v6 < 0 || !*a2 )
      return 1;
  }
  else
  {
    v6 = 1;
    if ( *((_QWORD *)this + 25) )
    {
      v7 = SysStringLen(*((BSTR *)this + 25));
      v8 = SysAllocStringLen(*((const OLECHAR **)this + 25), v7);
      *a2 = v8;
      return v8 == 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004d80  mov     [rsp+arg_0], rbx
0x140004d85  push    rdi
0x140004d86  sub     rsp, 20h
0x140004d8a  mov     rbx, rdx
0x140004d8d  mov     rdi, rcx
0x140004d90  test    rdx, rdx
0x140004d93  jnz     short loc_140004D9C
0x140004d95  mov     eax, 80004003h
0x140004d9a  jmp     short loc_140004E04
0x140004d9c  mov     qword ptr [rdx], 0
0x140004da3  mov     rcx, [rcx+50h]
0x140004da7  test    rcx, rcx
0x140004daa  jz      short loc_140004DCE
0x140004dac  mov     rax, [rcx]
0x140004daf  mov     rax, [rax+88h]
0x140004db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dbb  mov     ecx, eax
0x140004dbd  test    eax, eax
0x140004dbf  js      short loc_140004DC7
0x140004dc1  cmp     qword ptr [rbx], 0
0x140004dc5  jnz     short loc_140004E02
0x140004dc7  mov     ecx, 1
0x140004dcc  jmp     short loc_140004E02
0x140004dce  mov     rax, [rdi+0C8h]
0x140004dd5  mov     ecx, 1
0x140004dda  test    rax, rax
0x140004ddd  jz      short loc_140004E02
0x140004ddf  mov     rcx, rax; pbstr
0x140004de2  call    cs:__imp_SysStringLen
0x140004de8  mov     rcx, [rdi+0C8h]; strIn
0x140004def  mov     edx, eax; ui
0x140004df1  call    cs:__imp_SysAllocStringLen
0x140004df7  xor     ecx, ecx
0x140004df9  mov     [rbx], rax
0x140004dfc  test    rax, rax
0x140004dff  setz    cl
0x140004e02  mov     eax, ecx
0x140004e04  mov     rbx, [rsp+28h+arg_0]
0x140004e09  add     rsp, 20h
0x140004e0d  pop     rdi
0x140004e0e  retn
```
