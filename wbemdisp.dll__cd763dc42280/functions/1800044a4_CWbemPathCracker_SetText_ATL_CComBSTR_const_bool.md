# CWbemPathCracker::SetText(ATL::CComBSTR const &,bool)

- ea: `0x1800044a4`
- end: `0x1800045b7`
- name: `?SetText@CWbemPathCracker@@AEAAXAEBVCComBSTR@ATL@@_N@Z`
- size: `275`
- prototype: `void __fastcall(CWbemPathCracker *__hidden this, const struct ATL::CComBSTR *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001148c`
- `0x180032c08`

## callees

- `0x1800044a4`
- `0x180004d28`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000452e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000452e`
- `OLEAUT32!__imp_SysFreeString` at `0x180004583`
- `OLEAUT32!__imp_SysFreeString` at `0x180004583`
- `OLEAUT32!__imp_SysStringLen` at `0x1800044e2`
- `OLEAUT32!__imp_SysStringLen` at `0x180004544`
- `OLEAUT32!__imp_SysStringLen` at `0x180004551`
- `OLEAUT32!__imp_SysStringLen` at `0x18000458e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800044e2`
- `OLEAUT32!__imp_SysStringLen` at `0x180004544`
- `OLEAUT32!__imp_SysStringLen` at `0x180004551`
- `OLEAUT32!__imp_SysStringLen` at `0x18000458e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWbemPathCracker::SetText(CWbemPathCracker *this, BSTR *a2, unsigned __int8 a3)
{
  int v3; // esi
  BOOL TypeFromText; // eax
  unsigned int v7; // ebp
  BSTR v8; // rsi
  OLECHAR *v9; // rax
  OLECHAR *v10; // rbx

  v3 = a3;
  TypeFromText = CWbemPathCracker::GetTypeFromText(a2);
  if ( TypeFromText )
  {
    if ( TypeFromText && *((_QWORD *)this + 1) )
    {
      v7 = 8 * v3 + 4;
      if ( *a2 && SysStringLen(*a2) > 1 && **a2 == 123 && (v8 = *a2, v8[SysStringLen(*a2) - 1] == 125) )
      {
        v9 = SysAllocString(*a2 + 1);
        v10 = v9;
        if ( v9 && SysStringLen(v9) )
          v10[SysStringLen(v10) - 1] = 0;
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, OLECHAR *))(**((_QWORD **)this + 1) + 24LL))(
               *((_QWORD *)this + 1),
               v7,
               v10) >= 0 )
          *((_DWORD *)this + 7) = 1;
        SysFreeString(v10);
      }
      else if ( (*(int (__fastcall **)(_QWORD, _QWORD, BSTR))(**((_QWORD **)this + 1) + 24LL))(
                  *((_QWORD *)this + 1),
                  v7,
                  *a2) >= 0 )
      {
        *((_DWORD *)this + 7) = 1;
      }
    }
  }
  else
  {
    *((_DWORD *)this + 7) = 0;
  }
}

```

## disassembly

```asm
0x1800044a4  push    rbx
0x1800044a6  push    rbp
0x1800044a7  push    rsi
0x1800044a8  push    rdi
0x1800044a9  sub     rsp, 28h
0x1800044ad  movzx   esi, r8b
0x1800044b1  mov     rbx, rdx
0x1800044b4  mov     rdi, rcx
0x1800044b7  mov     rcx, rdx
0x1800044ba  call    ?GetTypeFromText@CWbemPathCracker@@CA?AW4WbemPathType@1@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::GetTypeFromText(ATL::CComBSTR const &)
0x1800044bf  test    eax, eax
0x1800044c1  jz      loc_1800045AB
0x1800044c7  cmp     eax, 1
0x1800044ca  jnz     short loc_18000451E
0x1800044cc  cmp     qword ptr [rdi+8], 0
0x1800044d1  jz      short loc_18000451E
0x1800044d3  lea     ebp, ds:4[rsi*8]
0x1800044da  mov     rcx, [rbx]; pbstr
0x1800044dd  test    rcx, rcx
0x1800044e0  jz      short loc_1800044FE
0x1800044e2  call    cs:__imp_SysStringLen
0x1800044e8  cmp     eax, 1
0x1800044eb  jbe     short loc_1800044FE
0x1800044ed  mov     rsi, [rbx]
0x1800044f0  mov     eax, 7Bh ; '{'
0x1800044f5  cmp     ax, [rsi]
0x1800044f8  jz      loc_18000458B
0x1800044fe  mov     rcx, [rdi+8]
0x180004502  mov     rax, [rcx]
0x180004505  mov     r8, [rbx]
0x180004508  mov     edx, ebp
0x18000450a  mov     rax, [rax+18h]
0x18000450e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004513  test    eax, eax
0x180004515  js      short loc_18000451E
0x180004517  mov     dword ptr [rdi+1Ch], 1
0x18000451e  add     rsp, 28h
0x180004522  pop     rdi
0x180004523  pop     rsi
0x180004524  pop     rbp
0x180004525  pop     rbx
0x180004526  retn
0x180004527  mov     rcx, [rbx]
0x18000452a  add     rcx, 2; psz
0x18000452e  call    cs:__imp_SysAllocString
0x180004534  mov     rbx, rax
0x180004537  mov     [rsp+48h+arg_18], rax
0x18000453c  test    rax, rax
0x18000453f  jz      short loc_180004560
0x180004541  mov     rcx, rax; pbstr
0x180004544  call    cs:__imp_SysStringLen
0x18000454a  test    eax, eax
0x18000454c  jz      short loc_180004560
0x18000454e  mov     rcx, rbx; pbstr
0x180004551  call    cs:__imp_SysStringLen
0x180004557  lea     ecx, [rax-1]
0x18000455a  xor     eax, eax
0x18000455c  mov     [rbx+rcx*2], ax
0x180004560  mov     rcx, [rdi+8]
0x180004564  mov     rax, [rcx]
0x180004567  mov     r8, rbx
0x18000456a  mov     edx, ebp
0x18000456c  mov     rax, [rax+18h]
0x180004570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004575  test    eax, eax
0x180004577  js      short loc_180004580
0x180004579  mov     dword ptr [rdi+1Ch], 1
0x180004580  mov     rcx, rbx; bstrString
0x180004583  call    cs:__imp_SysFreeString
0x180004589  jmp     short loc_18000451E
0x18000458b  mov     rcx, rsi; pbstr
0x18000458e  call    cs:__imp_SysStringLen
0x180004594  lea     ecx, [rax-1]
0x180004597  mov     eax, 7Dh ; '}'
0x18000459c  cmp     ax, [rsi+rcx*2]
0x1800045a0  jnz     loc_1800044FE
0x1800045a6  jmp     loc_180004527
0x1800045ab  mov     dword ptr [rdi+1Ch], 0
0x1800045b2  jmp     loc_18000451E
```
