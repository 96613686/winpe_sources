# CWbemPathCracker::GetServer(ATL::CComBSTR &)

- ea: `0x180010acc`
- end: `0x180010bb6`
- name: `?GetServer@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@@Z`
- size: `234`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, struct ATL::CComBSTR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e9a0`
- `0x18002eef0`
- `0x180033304`

## callees

- `0x180010acc`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010b69`
- `OLEAUT32!__imp_SysAllocString` at `0x180010b9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180010b69`
- `OLEAUT32!__imp_SysAllocString` at `0x180010b9d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010b32`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010b32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180010b83`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180010b83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CWbemPathCracker::GetServer(CWbemPathCracker *this, struct ATL::CComBSTR *a2)
{
  bool v4; // bl
  __int64 v5; // rcx
  OLECHAR *v6; // rax
  OLECHAR *v7; // rsi
  BSTR v8; // rax
  BSTR v10; // rax
  int v11; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v5 = *((_QWORD *)this + 1);
    if ( v5 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v5 + 56LL))(v5, &v11, 0);
      if ( v11 )
      {
        v6 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v11 + 1), 2u));
        v7 = v6;
        if ( v6 )
        {
          v6[v11] = 0;
          if ( (*(int (__fastcall **)(_QWORD, int *, OLECHAR *))(**((_QWORD **)this + 1) + 56LL))(
                 *((_QWORD *)this + 1),
                 &v11,
                 v6) >= 0 )
          {
            v8 = SysAllocString(v7);
            *(_QWORD *)a2 = v8;
            v4 = v8 != 0;
          }
          CWin32DefaultArena::WbemMemFree(v7);
        }
      }
      else
      {
        v10 = SysAllocString(&SystemName);
        *(_QWORD *)a2 = v10;
        return v10 != 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180010acc  push    rbx
0x180010ace  push    rsi
0x180010acf  push    rdi
0x180010ad0  push    r14
0x180010ad2  sub     rsp, 28h
0x180010ad6  mov     r14, rdx
0x180010ad9  mov     rdi, rcx
0x180010adc  xor     bl, bl
0x180010ade  cmp     dword ptr [rcx+1Ch], 1
0x180010ae2  jnz     loc_180010B8A
0x180010ae8  mov     rcx, [rcx+8]
0x180010aec  test    rcx, rcx
0x180010aef  jz      loc_180010B8A
0x180010af5  mov     [rsp+48h+arg_0], 0
0x180010afd  mov     rax, [rcx]
0x180010b00  xor     r8d, r8d
0x180010b03  lea     rdx, [rsp+48h+arg_0]
0x180010b08  mov     rax, [rax+38h]
0x180010b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b11  mov     eax, [rsp+48h+arg_0]
0x180010b15  test    eax, eax
0x180010b17  jz      short loc_180010B96
0x180010b19  lea     ecx, [rax+1]
0x180010b1c  mov     eax, 2
0x180010b21  mul     rcx
0x180010b24  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010b2b  cmovb   rax, rcx
0x180010b2f  mov     rcx, rax
0x180010b32  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010b38  mov     rsi, rax
0x180010b3b  test    rax, rax
0x180010b3e  jz      short loc_180010B8A
0x180010b40  mov     edx, [rsp+48h+arg_0]
0x180010b44  xor     ecx, ecx
0x180010b46  mov     [rax+rdx*2], cx
0x180010b4a  mov     rcx, [rdi+8]
0x180010b4e  mov     rdx, [rcx]
0x180010b51  mov     rax, [rdx+38h]
0x180010b55  mov     r8, rsi
0x180010b58  lea     rdx, [rsp+48h+arg_0]
0x180010b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b62  test    eax, eax
0x180010b64  js      short loc_180010B80
0x180010b66  mov     rcx, rsi; psz
0x180010b69  call    cs:__imp_SysAllocString
0x180010b6f  mov     [r14], rax
0x180010b72  movzx   ebx, bl
0x180010b75  mov     edx, 1
0x180010b7a  test    rax, rax
0x180010b7d  cmovnz  ebx, edx
0x180010b80  mov     rcx, rsi
0x180010b83  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180010b89  nop
0x180010b8a  mov     al, bl
0x180010b8c  add     rsp, 28h
0x180010b90  pop     r14
0x180010b92  pop     rdi
0x180010b93  pop     rsi
0x180010b94  pop     rbx
0x180010b95  retn
0x180010b96  lea     rcx, SystemName; psz
0x180010b9d  call    cs:__imp_SysAllocString
0x180010ba3  mov     [r14], rax
0x180010ba6  movzx   ebx, bl
0x180010ba9  mov     edx, 1
0x180010bae  test    rax, rax
0x180010bb1  cmovnz  ebx, edx
0x180010bb4  jmp     short loc_180010B8A
```
