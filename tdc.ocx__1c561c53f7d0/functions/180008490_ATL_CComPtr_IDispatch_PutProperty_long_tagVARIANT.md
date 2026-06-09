# ATL::CComPtr<IDispatch>::PutProperty(long,tagVARIANT *)

- ea: `0x180008490`
- end: `0x1800085a8`
- name: `?PutProperty@?$CComPtr@UIDispatch@@@ATL@@QEAAJJPEAUtagVARIANT@@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003514`

## callees

- `0x180008490`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IDispatch>::PutProperty(__int64 *a1, __int64 a2, _WORD *a3)
{
  unsigned int v3; // edi
  __int64 result; // rax
  __int64 v5; // rbx
  __int16 v6; // ax
  int v7; // [rsp+20h] [rbp-58h]
  _QWORD v8[2]; // [rsp+50h] [rbp-28h] BYREF
  int v9; // [rsp+60h] [rbp-18h]
  int v10; // [rsp+64h] [rbp-14h]
  int v11; // [rsp+80h] [rbp+8h] BYREF

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  v5 = *a1;
  if ( !*a1 )
    return 2147942487LL;
  v8[0] = a3;
  v9 = 1;
  v10 = 1;
  v8[1] = &v11;
  v6 = *a3 - 9;
  v11 = -3;
  if ( (v6 & 0xFFFB) != 0 && (*a3 & 0x6000) == 0
    || (result = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64, __int16, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 48LL))(
                   v5,
                   a2,
                   &GUID_NULL,
                   1024,
                   8,
                   v8,
                   0,
                   0,
                   0),
        (int)result < 0) )
  {
    LOWORD(v7) = 4;
    return (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64, int, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 48LL))(
             v5,
             v3,
             &GUID_NULL,
             1024,
             v7,
             v8,
             0,
             0,
             0);
  }
  return result;
}

```

## disassembly

```asm
0x180008490  mov     [rsp+arg_8], rbx
0x180008495  push    rdi
0x180008496  sub     rsp, 70h
0x18000849a  mov     edi, edx
0x18000849c  test    r8, r8
0x18000849f  jnz     short loc_1800084AB
0x1800084a1  mov     eax, 80004003h
0x1800084a6  jmp     loc_18000859A
0x1800084ab  mov     rbx, [rcx]
0x1800084ae  test    rbx, rbx
0x1800084b1  jnz     short loc_1800084BD
0x1800084b3  mov     eax, 80070057h
0x1800084b8  jmp     loc_18000859A
0x1800084bd  mov     eax, 1
0x1800084c2  mov     [rsp+78h+var_28], r8
0x1800084c7  mov     [rsp+78h+var_18], eax
0x1800084cb  mov     ecx, 0FFFBh
0x1800084d0  mov     [rsp+78h+var_14], eax
0x1800084d4  lea     rax, [rsp+78h+arg_0]
0x1800084dc  mov     [rsp+78h+var_20], rax
0x1800084e1  movzx   eax, word ptr [r8]
0x1800084e5  sub     ax, 9
0x1800084e9  mov     [rsp+78h+arg_0], 0FFFFFFFDh
0x1800084f4  test    cx, ax
0x1800084f7  jz      short loc_180008504
0x1800084f9  mov     eax, 6000h
0x1800084fe  test    [r8], ax
0x180008502  jz      short loc_180008550
0x180008504  mov     rax, [rbx]
0x180008507  lea     rcx, [rsp+78h+var_28]
0x18000850c  mov     [rsp+78h+var_38], 0
0x180008515  lea     r8, GUID_NULL
0x18000851c  mov     [rsp+78h+var_40], 0
0x180008525  mov     r9d, 400h
0x18000852b  mov     [rsp+78h+var_48], 0
0x180008534  mov     rax, [rax+30h]
0x180008538  mov     [rsp+78h+var_50], rcx
0x18000853d  mov     rcx, rbx
0x180008540  mov     [rsp+78h+var_58], 8
0x180008547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854c  test    eax, eax
0x18000854e  jns     short loc_18000859A
0x180008550  mov     rax, [rbx]
0x180008553  lea     rcx, [rsp+78h+var_28]
0x180008558  mov     [rsp+78h+var_38], 0
0x180008561  lea     r8, GUID_NULL
0x180008568  mov     [rsp+78h+var_40], 0
0x180008571  mov     r9d, 400h
0x180008577  mov     [rsp+78h+var_48], 0
0x180008580  mov     edx, edi
0x180008582  mov     rax, [rax+30h]
0x180008586  mov     [rsp+78h+var_50], rcx
0x18000858b  mov     rcx, rbx
0x18000858e  mov     [rsp+78h+var_58], 4
0x180008595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000859a  mov     rbx, [rsp+78h+arg_8]
0x1800085a2  add     rsp, 70h
0x1800085a6  pop     rdi
0x1800085a7  retn
```
