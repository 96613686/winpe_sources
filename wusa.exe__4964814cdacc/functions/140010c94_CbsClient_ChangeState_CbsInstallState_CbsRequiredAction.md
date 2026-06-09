# CbsClient::ChangeState(_CbsInstallState,_CbsRequiredAction *)

- ea: `0x140010c94`
- end: `0x140010e16`
- name: `?ChangeState@CbsClient@@QEAAJW4_CbsInstallState@@PEAW4_CbsRequiredAction@@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x14000afc0`

## callees

- `0x140001264`
- `0x14000e280`
- `0x140010c94`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010e05`
- `KERNEL32!LocalFree` at `0x140010e05`

## string_xrefs

- `0x140010d87`: `Failed to create a UI handler`

## pseudocode

```c
__int64 __fastcall CbsClient::ChangeState(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rax
  _DWORD *v6; // rdi
  signed int v7; // ebx
  HLOCAL v8; // rdi
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  if ( !*a1 || !a1[1] )
  {
    v7 = -2147418113;
    WusaLogDebugEventA(L"CbsClient::ChangeState", 341, "CBS session is not initialized.");
LABEL_16:
    hMem = 0;
    WusaGetErrorMessage(v7, (unsigned __int16 **)&hMem);
    v8 = hMem;
    WusaLogDebugEventA(L"CbsClient::ChangeState", 361, "Exit with error code 0X%x (%ls)", v7, (const wchar_t *)hMem);
    if ( v8 )
      LocalFree(v8);
    return (unsigned int)v7;
  }
  v5 = operator new(0x10u);
  v6 = v5;
  if ( !v5 )
  {
    WusaLogDebugEventA(L"CbsClient::ChangeState", 345, "Failed to create a UI handler");
    v7 = -2147024882;
    goto LABEL_16;
  }
  v5[1] = 1;
  *v5 = &CbsUIHandler::`vftable';
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD *))(*(_QWORD *)a1[1] + 88LL))(a1[1], 5, 0, v5);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 32LL))(*a1, a3);
    if ( *a1 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = 0;
    }
    if ( v7 >= 0 )
    {
      v7 = v6[3];
      if ( v7 < 0 )
        WusaLogDebugEventA(L"CbsClient::ChangeState", 355, "Failed to change state of a package");
    }
    else
    {
      WusaLogDebugEventA(L"CbsClient::ChangeState", 352, "Failed to finalize session");
    }
  }
  else
  {
    WusaLogDebugEventA(L"CbsClient::ChangeState", 348, "Failed to initiate changes");
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 < 0 )
    goto LABEL_16;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140010c94  push    rbx
0x140010c96  push    rbp
0x140010c97  push    rsi
0x140010c98  push    rdi
0x140010c99  sub     rsp, 38h
0x140010c9d  cmp     qword ptr [rcx], 0
0x140010ca1  mov     rbp, r8
0x140010ca4  mov     rsi, rcx
0x140010ca7  jz      loc_140010DA6
0x140010cad  cmp     qword ptr [rcx+8], 0
0x140010cb2  jz      loc_140010DA6
0x140010cb8  mov     ecx, 10h; Size
0x140010cbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010cc2  mov     rdi, rax
0x140010cc5  test    rax, rax
0x140010cc8  jz      loc_140010D87
0x140010cce  mov     qword ptr [rdi+8], 1
0x140010cd6  lea     rax, ??_7CbsUIHandler@@6B@; const CbsUIHandler::`vftable'
0x140010cdd  mov     [rdi], rax
0x140010ce0  xor     r8d, r8d
0x140010ce3  mov     rcx, [rsi+8]
0x140010ce7  mov     r9, rdi
0x140010cea  mov     rdx, [rcx]
0x140010ced  mov     rax, [rdx+58h]
0x140010cf1  lea     edx, [r8+5]
0x140010cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010cfa  mov     ebx, eax
0x140010cfc  test    eax, eax
0x140010cfe  jns     short loc_140010D0E
0x140010d00  lea     r8, aFailedToInitia_6; "Failed to initiate changes"
0x140010d07  mov     edx, 15Ch
0x140010d0c  jmp     short loc_140010D62
0x140010d0e  mov     rcx, [rsi]
0x140010d11  mov     rdx, rbp
0x140010d14  mov     rax, [rcx]
0x140010d17  mov     rax, [rax+20h]
0x140010d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d20  mov     rcx, [rsi]
0x140010d23  mov     ebx, eax
0x140010d25  test    rcx, rcx
0x140010d28  jz      short loc_140010D3D
0x140010d2a  mov     rax, [rcx]
0x140010d2d  mov     rax, [rax+10h]
0x140010d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d36  mov     qword ptr [rsi], 0
0x140010d3d  test    ebx, ebx
0x140010d3f  jns     short loc_140010D4F
0x140010d41  lea     r8, aFailedToFinali; "Failed to finalize session"
0x140010d48  mov     edx, 160h
0x140010d4d  jmp     short loc_140010D62
0x140010d4f  mov     ebx, [rdi+0Ch]
0x140010d52  test    ebx, ebx
0x140010d54  jns     short loc_140010D6E
0x140010d56  lea     r8, aFailedToChange; "Failed to change state of a package"
0x140010d5d  mov     edx, 163h
0x140010d62  lea     rcx, aCbsclientChang; "CbsClient::ChangeState"
0x140010d69  call    WusaLogDebugEventA
0x140010d6e  mov     rax, [rdi]
0x140010d71  mov     rcx, rdi
0x140010d74  mov     rax, [rax+10h]
0x140010d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d7d  test    ebx, ebx
0x140010d7f  jns     loc_140010E0B
0x140010d85  jmp     short loc_140010DC3
0x140010d87  lea     r8, aFailedToCreate_8; "Failed to create a UI handler"
0x140010d8e  mov     edx, 159h
0x140010d93  lea     rcx, aCbsclientChang; "CbsClient::ChangeState"
0x140010d9a  call    WusaLogDebugEventA
0x140010d9f  mov     ebx, 8007000Eh
0x140010da4  jmp     short loc_140010DC3
0x140010da6  lea     r8, aCbsSessionIsNo; "CBS session is not initialized."
0x140010dad  mov     edx, 155h
0x140010db2  lea     rcx, aCbsclientChang; "CbsClient::ChangeState"
0x140010db9  mov     ebx, 8000FFFFh
0x140010dbe  call    WusaLogDebugEventA
0x140010dc3  lea     rdx, [rsp+58h+hMem]; unsigned __int16 **
0x140010dc8  mov     [rsp+58h+hMem], 0
0x140010dd1  mov     ecx, ebx; dwMessageId
0x140010dd3  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140010dd8  mov     rdi, [rsp+58h+hMem]
0x140010ddd  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140010de4  mov     r9d, ebx
0x140010de7  mov     [rsp+58h+var_38], rdi
0x140010dec  mov     edx, 169h
0x140010df1  lea     rcx, aCbsclientChang; "CbsClient::ChangeState"
0x140010df8  call    WusaLogDebugEventA
0x140010dfd  test    rdi, rdi
0x140010e00  jz      short loc_140010E0B
0x140010e02  mov     rcx, rdi; hMem
0x140010e05  call    cs:__imp_LocalFree
0x140010e0b  mov     eax, ebx
0x140010e0d  add     rsp, 38h
0x140010e11  pop     rdi
0x140010e12  pop     rsi
0x140010e13  pop     rbp
0x140010e14  pop     rbx
0x140010e15  retn
```
