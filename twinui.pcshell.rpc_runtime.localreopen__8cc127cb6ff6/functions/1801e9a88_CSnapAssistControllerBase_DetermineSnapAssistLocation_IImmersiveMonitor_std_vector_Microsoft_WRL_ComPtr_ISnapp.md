# CSnapAssistControllerBase::_DetermineSnapAssistLocation(IImmersiveMonitor *,std::vector<Microsoft::WRL::ComPtr<ISnappedWindow>,std::allocator<Microsoft::WRL::ComPtr<ISnappedWindow>>> const &,tagRECT *)

- ea: `0x1801e9a88`
- end: `0x1801e9cc8`
- name: `?_DetermineSnapAssistLocation@CSnapAssistControllerBase@@IEAAJPEAUIImmersiveMonitor@@AEBV?$vector@V?$ComPtr@UISnappedWindow@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UISnappedWindow@@@WRL@Microsoft@@@std@@@std@@PEAUtagRECT@@@Z`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18018ef10`

## callees

- `0x1800237c8`
- `0x1801e9a88`
- `0x1802bbaf8`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1801e9abc`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1801e9abc`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1801e9c8e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1801e9c8e`
- `ext-ms-win-gdi-rgn-l1-1-0!GetRgnBox` at `0x1801e9c54`
- `ext-ms-win-gdi-rgn-l1-1-0!GetRgnBox` at `0x1801e9c54`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9b0c`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9b67`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9be8`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9b0c`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9b67`
- `GDI32!CreateRectRgnIndirect` at `0x1801e9be8`
- `GDI32!DeleteObject` at `0x1801e9c11`
- `GDI32!DeleteObject` at `0x1801e9c36`
- `GDI32!DeleteObject` at `0x1801e9c47`
- `GDI32!DeleteObject` at `0x1801e9c7a`
- `GDI32!DeleteObject` at `0x1801e9c99`
- `GDI32!DeleteObject` at `0x1801e9c11`
- `GDI32!DeleteObject` at `0x1801e9c36`
- `GDI32!DeleteObject` at `0x1801e9c47`
- `GDI32!DeleteObject` at `0x1801e9c7a`
- `GDI32!DeleteObject` at `0x1801e9c99`
- `GDI32!CombineRgn` at `0x1801e9ba4`
- `GDI32!CombineRgn` at `0x1801e9c05`
- `GDI32!CombineRgn` at `0x1801e9ba4`
- `GDI32!CombineRgn` at `0x1801e9c05`

## string_xrefs

- `0x1801e9ae9`: `pcshell\twinui\snapcomponent\lib\snapassistcontroller.cpp`
- `0x1801e9b22`: `pcshell\twinui\snapcomponent\lib\snapassistcontroller.cpp`
- `0x1801e9b7d`: `pcshell\twinui\snapcomponent\lib\snapassistcontroller.cpp`
- `0x1801e9c20`: `pcshell\twinui\snapcomponent\lib\snapassistcontroller.cpp`
- `0x1801e9c62`: `pcshell\twinui\snapcomponent\lib\snapassistcontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSnapAssistControllerBase::_DetermineSnapAssistLocation(
        __int64 a1,
        __int64 a2,
        _QWORD **a3,
        struct tagRECT *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  HRGN v10; // rbx
  const char *v11; // r9
  HRGN v12; // rax
  const char *v13; // r9
  HRGN v14; // rdi
  unsigned int LastError; // esi
  unsigned int v16; // r14d
  unsigned __int64 v17; // r12
  HRGN v18; // rax
  const char *v19; // r9
  HRGN v20; // rsi
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-60h]
  RECT rect; // [rsp+30h] [rbp-50h] BYREF
  struct tagRECT rc; // [rsp+40h] [rbp-40h] BYREF
  RECT v25; // [rsp+50h] [rbp-30h] BYREF
  RECT v26; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  SetRectEmpty(a4);
  rect = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, RECT *))(*(_QWORD *)a2 + 88LL))(a2, &rect);
  v8 = v7;
  if ( v7 >= 0 )
  {
    rc = 0;
    v10 = CreateRectRgnIndirect(&rect);
    if ( v10 )
    {
      if ( a3[1] - *a3 )
      {
        (*(void (__fastcall **)(_QWORD, RECT *))(*(_QWORD *)**a3 + 56LL))(**a3, &v25);
        v12 = CreateRectRgnIndirect(&v25);
        v14 = v12;
        if ( v12 )
        {
          v16 = CombineRgn(v10, v10, v12, 4);
          v17 = 1;
          while ( v16 > 1 )
          {
            if ( v17 >= a3[1] - *a3 )
            {
              if ( v16 == 2 )
              {
                DeleteObject(v14);
                goto LABEL_16;
              }
              break;
            }
            (*(void (__fastcall **)(_QWORD, RECT *))(*(_QWORD *)(*a3)[v17] + 56LL))((*a3)[v17], &v26);
            v18 = CreateRectRgnIndirect(&v26);
            v20 = v18;
            if ( !v18 )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x3D9,
                            (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\snapassistcontroller.cpp",
                            v19);
              DeleteObject(v14);
              goto LABEL_20;
            }
            v16 = CombineRgn(v10, v10, v18, 4);
            DeleteObject(v20);
            ++v17;
          }
          DeleteObject(v14);
          LastError = -2147019873;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x3D0,
                        (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\snapassistcontroller.cpp",
                        v13);
        }
      }
      else
      {
LABEL_16:
        if ( GetRgnBox(v10, &rc) )
        {
          CopyRect(a4, &rc);
          LastError = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x3E1,
                        (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\snapassistcontroller.cpp",
                        v21);
        }
      }
LABEL_20:
      DeleteObject(v10);
      return LastError;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x3C7,
               (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\snapassistcontroller.cpp",
               v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\snapassistcontroller.cpp",
      (const char *)(unsigned int)v7,
      v22);
    return v8;
  }
}

```

## disassembly

```asm
0x1801e9a88  mov     [rsp-38h+arg_0], rbx
0x1801e9a8d  push    rbp
0x1801e9a8e  push    rsi
0x1801e9a8f  push    rdi
0x1801e9a90  push    r12
0x1801e9a92  push    r13
0x1801e9a94  push    r14
0x1801e9a96  push    r15
0x1801e9a98  mov     rbp, rsp
0x1801e9a9b  sub     rsp, 80h
0x1801e9aa2  mov     rax, cs:__security_cookie
0x1801e9aa9  xor     rax, rsp
0x1801e9aac  mov     [rbp+var_10], rax
0x1801e9ab0  mov     r13, r9
0x1801e9ab3  mov     r15, r8
0x1801e9ab6  mov     rbx, rdx
0x1801e9ab9  mov     rcx, r9; lprc
0x1801e9abc  call    cs:__imp_SetRectEmpty
0x1801e9ac2  xorps   xmm0, xmm0
0x1801e9ac5  movups  xmmword ptr [rbp+rect.left], xmm0
0x1801e9ac9  mov     rax, [rbx]
0x1801e9acc  lea     rdx, [rbp+rect]
0x1801e9ad0  mov     rcx, rbx
0x1801e9ad3  mov     rax, [rax+58h]
0x1801e9ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9adc  mov     ebx, eax
0x1801e9ade  test    eax, eax
0x1801e9ae0  jns     short loc_1801E9B01
0x1801e9ae2  mov     rcx, [rbp+38h]; this
0x1801e9ae6  mov     r9d, eax; char *
0x1801e9ae9  lea     r8, aPcshellTwinuiS; "pcshell\\twinui\\snapcomponent\\lib\\sn"...
0x1801e9af0  mov     edx, 3C0h; void *
0x1801e9af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e9afa  mov     eax, ebx
0x1801e9afc  jmp     loc_1801E9CA1
0x1801e9b01  xorps   xmm0, xmm0
0x1801e9b04  movups  xmmword ptr [rbp+rc.left], xmm0
0x1801e9b08  lea     rcx, [rbp+rect]; lprect
0x1801e9b0c  call    cs:__imp_CreateRectRgnIndirect
0x1801e9b12  mov     rbx, rax
0x1801e9b15  mov     [rbp+var_60], rax
0x1801e9b19  test    rax, rax
0x1801e9b1c  jnz     short loc_1801E9B39
0x1801e9b1e  mov     rcx, [rbp+38h]; this
0x1801e9b22  lea     r8, aPcshellTwinuiS; "pcshell\\twinui\\snapcomponent\\lib\\sn"...
0x1801e9b29  mov     edx, 3C7h; void *
0x1801e9b2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e9b33  nop
0x1801e9b34  jmp     loc_1801E9CA1
0x1801e9b39  mov     rcx, [r15]
0x1801e9b3c  mov     rax, [r15+8]
0x1801e9b40  sub     rax, rcx
0x1801e9b43  sar     rax, 3
0x1801e9b47  test    rax, rax
0x1801e9b4a  jz      loc_1801E9C4D
0x1801e9b50  mov     rcx, [rcx]
0x1801e9b53  mov     rax, [rcx]
0x1801e9b56  lea     rdx, [rbp+var_30]
0x1801e9b5a  mov     rax, [rax+38h]
0x1801e9b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9b63  lea     rcx, [rbp+var_30]; lprect
0x1801e9b67  call    cs:__imp_CreateRectRgnIndirect
0x1801e9b6d  mov     rdi, rax
0x1801e9b70  mov     [rbp+var_58], rax
0x1801e9b74  test    rax, rax
0x1801e9b77  jnz     short loc_1801E9B95
0x1801e9b79  mov     rcx, [rbp+38h]; this
0x1801e9b7d  lea     r8, aPcshellTwinuiS; "pcshell\\twinui\\snapcomponent\\lib\\sn"...
0x1801e9b84  mov     edx, 3D0h; void *
0x1801e9b89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e9b8e  mov     esi, eax
0x1801e9b90  jmp     loc_1801E9C96
0x1801e9b95  mov     r9d, 4; iMode
0x1801e9b9b  mov     r8, rdi; hrgnSrc2
0x1801e9b9e  mov     rdx, rbx; hrgnSrc1
0x1801e9ba1  mov     rcx, rbx; hrgnDst
0x1801e9ba4  call    cs:__imp_CombineRgn
0x1801e9baa  mov     r14d, eax
0x1801e9bad  mov     r12d, 1
0x1801e9bb3  cmp     r14d, 1
0x1801e9bb7  jbe     loc_1801E9C77
0x1801e9bbd  mov     rax, [r15]
0x1801e9bc0  mov     rcx, [r15+8]
0x1801e9bc4  sub     rcx, rax
0x1801e9bc7  sar     rcx, 3
0x1801e9bcb  cmp     r12, rcx
0x1801e9bce  jnb     short loc_1801E9C3E
0x1801e9bd0  mov     rcx, [rax+r12*8]
0x1801e9bd4  mov     rax, [rcx]
0x1801e9bd7  lea     rdx, [rbp+var_20]
0x1801e9bdb  mov     rax, [rax+38h]
0x1801e9bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9be4  lea     rcx, [rbp+var_20]; lprect
0x1801e9be8  call    cs:__imp_CreateRectRgnIndirect
0x1801e9bee  mov     rsi, rax
0x1801e9bf1  test    rax, rax
0x1801e9bf4  jz      short loc_1801E9C1C
0x1801e9bf6  mov     r9d, 4; iMode
0x1801e9bfc  mov     r8, rax; hrgnSrc2
0x1801e9bff  mov     rdx, rbx; hrgnSrc1
0x1801e9c02  mov     rcx, rbx; hrgnDst
0x1801e9c05  call    cs:__imp_CombineRgn
0x1801e9c0b  mov     r14d, eax
0x1801e9c0e  mov     rcx, rsi; ho
0x1801e9c11  call    cs:__imp_DeleteObject
0x1801e9c17  inc     r12
0x1801e9c1a  jmp     short loc_1801E9BB3
0x1801e9c1c  mov     rcx, [rbp+38h]; this
0x1801e9c20  lea     r8, aPcshellTwinuiS; "pcshell\\twinui\\snapcomponent\\lib\\sn"...
0x1801e9c27  mov     edx, 3D9h; void *
0x1801e9c2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e9c31  mov     esi, eax
0x1801e9c33  mov     rcx, rdi; ho
0x1801e9c36  call    cs:__imp_DeleteObject
0x1801e9c3c  jmp     short loc_1801E9C96
0x1801e9c3e  cmp     r14d, 2
0x1801e9c42  jnz     short loc_1801E9C77
0x1801e9c44  mov     rcx, rdi; ho
0x1801e9c47  call    cs:__imp_DeleteObject
0x1801e9c4d  lea     rdx, [rbp+rc]; lprc
0x1801e9c51  mov     rcx, rbx; hrgn
0x1801e9c54  call    cs:__imp_GetRgnBox
0x1801e9c5a  test    eax, eax
0x1801e9c5c  jnz     short loc_1801E9C87
0x1801e9c5e  mov     rcx, [rbp+38h]; this
0x1801e9c62  lea     r8, aPcshellTwinuiS; "pcshell\\twinui\\snapcomponent\\lib\\sn"...
0x1801e9c69  mov     edx, 3E1h; void *
0x1801e9c6e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e9c73  mov     esi, eax
0x1801e9c75  jmp     short loc_1801E9C96
0x1801e9c77  mov     rcx, rdi; ho
0x1801e9c7a  call    cs:__imp_DeleteObject
0x1801e9c80  mov     esi, 8007139Fh
0x1801e9c85  jmp     short loc_1801E9C96
0x1801e9c87  lea     rdx, [rbp+rc]; lprcSrc
0x1801e9c8b  mov     rcx, r13; lprcDst
0x1801e9c8e  call    cs:__imp_CopyRect
0x1801e9c94  xor     esi, esi
0x1801e9c96  mov     rcx, rbx; ho
0x1801e9c99  call    cs:__imp_DeleteObject
0x1801e9c9f  mov     eax, esi
0x1801e9ca1  mov     rcx, [rbp+var_10]
0x1801e9ca5  xor     rcx, rsp; StackCookie
0x1801e9ca8  call    __security_check_cookie
0x1801e9cad  mov     rbx, [rsp+80h+arg_0]
0x1801e9cb5  add     rsp, 80h
0x1801e9cbc  pop     r15
0x1801e9cbe  pop     r14
0x1801e9cc0  pop     r13
0x1801e9cc2  pop     r12
0x1801e9cc4  pop     rdi
0x1801e9cc5  pop     rsi
0x1801e9cc6  pop     rbp
0x1801e9cc7  retn
```
