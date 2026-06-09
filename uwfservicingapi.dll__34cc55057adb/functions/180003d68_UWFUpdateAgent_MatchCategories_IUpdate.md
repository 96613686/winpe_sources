# UWFUpdateAgent::MatchCategories(IUpdate *)

- ea: `0x180003d68`
- end: `0x180003fff`
- name: `?MatchCategories@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdate *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000490c`

## callees

- `0x180001536`
- `0x180002570`
- `0x180002db0`
- `0x180003d68`
- `0x180006010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003e9d`
- `msvcrt!_wcsicmp` at `0x180003f86`
- `msvcrt!_wcsicmp` at `0x180003e9d`
- `msvcrt!_wcsicmp` at `0x180003f86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fa3`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fa3`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::MatchCategories(UWFUpdateAgent *this, struct IUpdate *a2)
{
  unsigned int v4; // r14d
  unsigned __int16 **v5; // rsi
  unsigned __int16 *v6; // r12
  LSTATUS MultiString; // eax
  DWORD v8; // ecx
  unsigned __int64 v9; // rdi
  size_t v10; // rax
  size_t v11; // rax
  const unsigned __int16 *v12; // rdx
  HKEY v13; // rcx
  LSTATUS v14; // eax
  int v15; // r15d
  signed int v16; // eax
  unsigned int v17; // edi
  int v18; // ebx
  int v19; // ebx
  UWFUpdateAgent *v20; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+48h] BYREF
  int v22; // [rsp+90h] [rbp+50h] BYREF
  __int64 v23; // [rsp+98h] [rbp+58h] BYREF

  v20 = this;
  if ( !a2 )
    return 0;
  v23 = 0;
  v4 = 0;
  v5 = 0;
  LODWORD(v20) = 0;
  v6 = 0;
  LODWORD(String1) = 0;
  MultiString = UwfServicingRegGetMultiString(
                  (HKEY)this,
                  (const unsigned __int16 *)a2,
                  L"Categories",
                  0,
                  (int *)&String1,
                  0,
                  (int *)&v20);
  v8 = MultiString;
  if ( MultiString < 0 )
  {
    if ( (MultiString & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)MultiString;
    goto LABEL_37;
  }
  if ( (_DWORD)String1 )
  {
    v9 = (int)v20;
    if ( (_DWORD)v20 )
    {
      v10 = 2LL * (int)String1;
      if ( !is_mul_ok((int)String1, 2u) )
        v10 = -1;
      v6 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v6 )
        goto LABEL_11;
      v11 = 8 * v9;
      if ( !is_mul_ok(v9, 8u) )
        v11 = -1;
      v5 = (unsigned __int16 **)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        v14 = UwfServicingRegGetMultiString(v13, v12, L"Categories", v6, (int *)&String1, v5, (int *)&v20);
        if ( v14 >= 0 )
        {
          v15 = (int)v20;
          if ( (_DWORD)v20 == 1 && !_wcsicmp(*v5, L"*") )
          {
            v4 = v15;
            goto LABEL_38;
          }
          v14 = ((__int64 (__fastcall *)(struct IUpdate *, __int64 *))a2->lpVtbl->get_Categories)(a2, &v23);
          if ( v14 >= 0 && v23 )
          {
            v22 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 72LL))(v23, &v22);
            if ( v16 < 0 )
            {
              SetLastError(v16);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              goto LABEL_38;
            }
            v17 = 0;
            if ( v22 <= 0 )
              goto LABEL_38;
            while ( 1 )
            {
              v20 = 0;
              v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, UWFUpdateAgent **))(*(_QWORD *)v23 + 56LL))(
                      v23,
                      v17,
                      &v20);
              if ( v14 < 0 || !v20 )
                break;
              String1 = 0;
              v18 = (*(__int64 (__fastcall **)(UWFUpdateAgent *, wchar_t **))(*(_QWORD *)v20 + 56LL))(v20, &String1);
              (*(void (__fastcall **)(UWFUpdateAgent *))(*(_QWORD *)v20 + 16LL))(v20);
              if ( v18 < 0 )
              {
                v8 = v18;
                goto LABEL_37;
              }
              v19 = 0;
              if ( v15 > 0 )
              {
                while ( _wcsicmp(String1, v5[v19]) )
                {
                  if ( ++v19 >= v15 )
                    goto LABEL_32;
                }
                v4 = 1;
              }
LABEL_32:
              SysFreeString(String1);
              if ( v4 != 1 && (int)++v17 < v22 )
                continue;
              goto LABEL_38;
            }
          }
        }
        v8 = v14;
      }
      else
      {
LABEL_11:
        v8 = 14;
      }
LABEL_37:
      SetLastError(v8);
    }
  }
LABEL_38:
  operator delete(v6);
  operator delete(v5);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  return v4;
}

```

## disassembly

```asm
0x180003d68  mov     [rsp-38h+arg_0], rcx
0x180003d6d  push    rbp
0x180003d6e  push    rbx
0x180003d6f  push    rsi
0x180003d70  push    rdi
0x180003d71  push    r12
0x180003d73  push    r14
0x180003d75  push    r15
0x180003d77  mov     rbp, rsp
0x180003d7a  sub     rsp, 40h
0x180003d7e  mov     rbx, rdx
0x180003d81  test    rdx, rdx
0x180003d84  jnz     short loc_180003D8D
0x180003d86  xor     eax, eax
0x180003d88  jmp     loc_180003FF0
0x180003d8d  lea     rax, [rbp+arg_0]
0x180003d91  mov     [rbp+arg_18], 0
0x180003d99  mov     [rsp+40h+var_10], rax; int *
0x180003d9e  lea     r8, aCategories; "Categories"
0x180003da5  lea     rax, [rbp+String1]
0x180003da9  xor     r14d, r14d
0x180003dac  xor     esi, esi
0x180003dae  mov     dword ptr [rbp+arg_0], r14d
0x180003db2  mov     [rsp+40h+var_18], rsi; unsigned __int16 **
0x180003db7  xor     r9d, r9d; unsigned __int16 *
0x180003dba  mov     [rsp+40h+var_20], rax; int *
0x180003dbf  xor     r12d, r12d
0x180003dc2  mov     dword ptr [rbp+String1], r14d
0x180003dc6  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180003dcb  mov     ecx, eax
0x180003dcd  test    eax, eax
0x180003dcf  jns     short loc_180003DE9
0x180003dd1  and     eax, 1FFF0000h
0x180003dd6  cmp     eax, 70000h
0x180003ddb  jnz     loc_180003FC2
0x180003de1  movzx   ecx, cx
0x180003de4  jmp     loc_180003FC2
0x180003de9  movsxd  rax, dword ptr [rbp+String1]
0x180003ded  test    eax, eax
0x180003def  jz      loc_180003FC8
0x180003df5  movsxd  rdi, dword ptr [rbp+arg_0]
0x180003df9  test    edi, edi
0x180003dfb  jz      loc_180003FC8
0x180003e01  mov     rcx, rax
0x180003e04  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003e0b  mov     eax, 2
0x180003e10  mul     rcx
0x180003e13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e1a  cmovb   rax, r15
0x180003e1e  mov     rcx, rax; unsigned __int64
0x180003e21  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003e26  mov     r12, rax
0x180003e29  test    rax, rax
0x180003e2c  jnz     short loc_180003E38
0x180003e2e  mov     ecx, 0Eh
0x180003e33  jmp     loc_180003FC2
0x180003e38  mov     eax, 8
0x180003e3d  mul     rdi
0x180003e40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e47  cmovb   rax, r15
0x180003e4b  mov     rcx, rax; unsigned __int64
0x180003e4e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003e53  mov     rsi, rax
0x180003e56  test    rax, rax
0x180003e59  jz      short loc_180003E2E
0x180003e5b  lea     rax, [rbp+arg_0]
0x180003e5f  mov     r9, r12; unsigned __int16 *
0x180003e62  mov     [rsp+40h+var_10], rax; int *
0x180003e67  lea     r8, aCategories; "Categories"
0x180003e6e  lea     rax, [rbp+String1]
0x180003e72  mov     [rsp+40h+var_18], rsi; unsigned __int16 **
0x180003e77  mov     [rsp+40h+var_20], rax; int *
0x180003e7c  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180003e81  test    eax, eax
0x180003e83  js      loc_180003FC0
0x180003e89  mov     r15d, dword ptr [rbp+arg_0]
0x180003e8d  cmp     r15d, 1
0x180003e91  jnz     short loc_180003EAF
0x180003e93  mov     rcx, [rsi]; String1
0x180003e96  lea     rdx, String2; "*"
0x180003e9d  call    cs:__imp__wcsicmp
0x180003ea3  test    eax, eax
0x180003ea5  jnz     short loc_180003EAF
0x180003ea7  mov     r14d, r15d
0x180003eaa  jmp     loc_180003FC8
0x180003eaf  mov     rax, [rbx]
0x180003eb2  lea     rdx, [rbp+arg_18]
0x180003eb6  mov     rcx, rbx
0x180003eb9  mov     rax, [rax+58h]
0x180003ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec2  test    eax, eax
0x180003ec4  js      loc_180003FC0
0x180003eca  mov     rcx, [rbp+arg_18]
0x180003ece  test    rcx, rcx
0x180003ed1  jz      loc_180003FC0
0x180003ed7  mov     [rbp+arg_10], r14d
0x180003edb  lea     rdx, [rbp+arg_10]
0x180003edf  mov     rax, [rcx]
0x180003ee2  mov     rax, [rax+48h]
0x180003ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eeb  test    eax, eax
0x180003eed  jns     short loc_180003F0C
0x180003eef  mov     ecx, eax; dwErrCode
0x180003ef1  call    cs:__imp_SetLastError
0x180003ef7  mov     rcx, [rbp+arg_18]
0x180003efb  mov     rax, [rcx]
0x180003efe  mov     rax, [rax+10h]
0x180003f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f07  jmp     loc_180003FC8
0x180003f0c  xor     edi, edi
0x180003f0e  cmp     [rbp+arg_10], edi
0x180003f11  jle     loc_180003FC8
0x180003f17  mov     rcx, [rbp+arg_18]
0x180003f1b  lea     r8, [rbp+arg_0]
0x180003f1f  mov     [rbp+arg_0], 0
0x180003f27  mov     edx, edi
0x180003f29  mov     rax, [rcx]
0x180003f2c  mov     rax, [rax+38h]
0x180003f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f35  test    eax, eax
0x180003f37  js      loc_180003FC0
0x180003f3d  mov     rcx, [rbp+arg_0]
0x180003f41  test    rcx, rcx
0x180003f44  jz      short loc_180003FC0
0x180003f46  mov     [rbp+String1], 0
0x180003f4e  lea     rdx, [rbp+String1]
0x180003f52  mov     rax, [rcx]
0x180003f55  mov     rax, [rax+38h]
0x180003f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f5e  mov     rcx, [rbp+arg_0]
0x180003f62  mov     ebx, eax
0x180003f64  mov     rax, [rcx]
0x180003f67  mov     rax, [rax+10h]
0x180003f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f70  test    ebx, ebx
0x180003f72  js      short loc_180003FBC
0x180003f74  xor     ebx, ebx
0x180003f76  test    r15d, r15d
0x180003f79  jle     short loc_180003F9F
0x180003f7b  mov     rcx, [rbp+String1]; String1
0x180003f7f  movsxd  rdx, ebx
0x180003f82  mov     rdx, [rsi+rdx*8]; String2
0x180003f86  call    cs:__imp__wcsicmp
0x180003f8c  test    eax, eax
0x180003f8e  jz      short loc_180003F99
0x180003f90  inc     ebx
0x180003f92  cmp     ebx, r15d
0x180003f95  jl      short loc_180003F7B
0x180003f97  jmp     short loc_180003F9F
0x180003f99  mov     r14d, 1
0x180003f9f  mov     rcx, [rbp+String1]; bstrString
0x180003fa3  call    cs:__imp_SysFreeString
0x180003fa9  cmp     r14d, 1
0x180003fad  jz      short loc_180003FC8
0x180003faf  inc     edi
0x180003fb1  cmp     edi, [rbp+arg_10]
0x180003fb4  jl      loc_180003F17
0x180003fba  jmp     short loc_180003FC8
0x180003fbc  mov     ecx, ebx
0x180003fbe  jmp     short loc_180003FC2
0x180003fc0  mov     ecx, eax; dwErrCode
0x180003fc2  call    cs:__imp_SetLastError
0x180003fc8  mov     rcx, r12; void *
0x180003fcb  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180003fd0  mov     rcx, rsi; void *
0x180003fd3  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180003fd8  mov     rcx, [rbp+arg_18]
0x180003fdc  test    rcx, rcx
0x180003fdf  jz      short loc_180003FED
0x180003fe1  mov     rdx, [rcx]
0x180003fe4  mov     rax, [rdx+10h]
0x180003fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fed  mov     eax, r14d
0x180003ff0  add     rsp, 40h
0x180003ff4  pop     r15
0x180003ff6  pop     r14
0x180003ff8  pop     r12
0x180003ffa  pop     rdi
0x180003ffb  pop     rsi
0x180003ffc  pop     rbx
0x180003ffd  pop     rbp
0x180003ffe  retn
```
