# CScriptFile::Create(ushort const *,IDebugApplication64 *,CScriptFile * *)

- ea: `0x14000a974`
- end: `0x14000ab4d`
- name: `?Create@CScriptFile@@SAJPEBGPEAUIDebugApplication64@@PEAPEAV1@@Z`
- size: `473`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IDebugApplication64 *, struct CScriptFile **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007dc8`

## callees

- `0x140001008`
- `0x14000a974`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000aa68`
- `OLEAUT32!__imp_SysAllocString` at `0x14000aa68`

## pseudocode

```c
__int64 __fastcall CScriptFile::Create(OLECHAR *psz, struct IDebugApplication64 *a2, struct CScriptFile **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  BSTR v8; // rax
  int v9; // edi
  _QWORD *v10; // r15
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  if ( psz && a3 )
  {
    v12 = 0;
    v6 = operator new(0x88u);
    v7 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
    v6[9] = 0;
    v6[7] = 0;
    v6[8] = 0;
    *((_DWORD *)v6 + 20) = 0;
    v6[2] = &CUnknown::`vftable';
    v6[5] = &CUnknown::InnerUnknown::`vftable';
    *((_DWORD *)v6 + 12) = 1;
    v6[3] = v6 + 5;
    v6[4] = v6;
    _InterlockedIncrement(&Global::g_cObjects);
    v6[11] = 0;
    *v6 = &CScriptFile::`vftable'{for `IDebugDocumentText'};
    *((_DWORD *)v6 + 20) = 0;
    v6[1] = &CScriptFile::`vftable'{for `IDebugDocumentProvider'};
    v6[2] = &CScriptFile::`vftable'{for `CUnknown'};
    *((_DWORD *)v6 + 32) = -1;
    *((_DWORD *)v6 + 33) = -1;
    v6[12] = 0;
    v6[14] = 0;
    v6[15] = 0;
    v8 = SysAllocString(psz);
    v7[12] = v8;
    if ( v8 )
    {
      if ( !a2
        || (v10 = v7 + 15,
            v9 = ((__int64 (__fastcall *)(struct IDebugApplication64 *, _QWORD *))a2->lpVtbl->CreateApplicationNode)(
                   a2,
                   v7 + 15),
            v9 >= 0)
        && (v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v10 + 64LL))(
                   *v10,
                   (unsigned __int64)(v7 + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)v7 >> 64)),
            v9 >= 0)
        && (v9 = ((__int64 (__fastcall *)(struct IDebugApplication64 *, __int64 *))a2->lpVtbl->GetRootNode)(a2, &v12),
            v9 >= 0)
        && (v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v10 + 80LL))(*v10, v12),
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12),
            v9 >= 0) )
      {
        *a3 = (struct CScriptFile *)v7;
        return 0;
      }
    }
    else
    {
      v9 = -2147024882;
    }
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    return (unsigned int)v9;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x14000a974  mov     [rsp+arg_8], rbx
0x14000a979  mov     [rsp+arg_10], rsi
0x14000a97e  push    rdi
0x14000a97f  push    r14
0x14000a981  push    r15
0x14000a983  sub     rsp, 20h
0x14000a987  mov     r14, r8
0x14000a98a  mov     rsi, rdx
0x14000a98d  mov     rdi, rcx
0x14000a990  test    rcx, rcx
0x14000a993  jz      loc_14000AB34
0x14000a999  test    r8, r8
0x14000a99c  jz      loc_14000AB34
0x14000a9a2  mov     ecx, 88h; Size
0x14000a9a7  mov     [rsp+38h+arg_0], 0
0x14000a9b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a9b5  mov     rbx, rax
0x14000a9b8  test    rax, rax
0x14000a9bb  jz      loc_14000AB2B
0x14000a9c1  mov     qword ptr [rax+48h], 0
0x14000a9c9  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x14000a9d0  mov     qword ptr [rax+38h], 0
0x14000a9d8  mov     qword ptr [rax+40h], 0
0x14000a9e0  mov     dword ptr [rax+50h], 0
0x14000a9e7  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x14000a9ee  mov     [rbx+10h], rax
0x14000a9f2  lea     rax, [rbx+28h]
0x14000a9f6  mov     [rax], rcx
0x14000a9f9  mov     dword ptr [rax+8], 1
0x14000aa00  mov     [rbx+18h], rax
0x14000aa04  mov     [rbx+20h], rbx
0x14000aa08  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x14000aa0f  lea     rax, ??_7CScriptFile@@6BIDebugDocumentText@@@; const CScriptFile::`vftable'{for `IDebugDocumentText'}
0x14000aa16  mov     qword ptr [rbx+58h], 0
0x14000aa1e  mov     [rbx], rax
0x14000aa21  mov     rcx, rdi; psz
0x14000aa24  lea     rax, ??_7CScriptFile@@6BIDebugDocumentProvider@@@; const CScriptFile::`vftable'{for `IDebugDocumentProvider'}
0x14000aa2b  mov     dword ptr [rbx+50h], 0
0x14000aa32  mov     [rbx+8], rax
0x14000aa36  lea     rax, ??_7CScriptFile@@6BCUnknown@@@; const CScriptFile::`vftable'{for `CUnknown'}
0x14000aa3d  mov     [rbx+10h], rax
0x14000aa41  or      eax, 0FFFFFFFFh
0x14000aa44  mov     [rbx+80h], eax
0x14000aa4a  mov     [rbx+84h], eax
0x14000aa50  mov     qword ptr [rbx+60h], 0
0x14000aa58  mov     qword ptr [rbx+70h], 0
0x14000aa60  mov     qword ptr [rbx+78h], 0
0x14000aa68  call    cs:__imp_SysAllocString
0x14000aa6e  mov     [rbx+60h], rax
0x14000aa72  test    rax, rax
0x14000aa75  jnz     short loc_14000AA81
0x14000aa77  mov     edi, 8007000Eh
0x14000aa7c  jmp     loc_14000AB13
0x14000aa81  test    rsi, rsi
0x14000aa84  jz      loc_14000AB24
0x14000aa8a  mov     rax, [rsi]
0x14000aa8d  lea     r15, [rbx+78h]
0x14000aa91  mov     rdx, r15
0x14000aa94  mov     rcx, rsi
0x14000aa97  mov     rax, [rax+0D8h]
0x14000aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaa3  mov     edi, eax
0x14000aaa5  test    eax, eax
0x14000aaa7  js      short loc_14000AB13
0x14000aaa9  mov     rcx, [r15]
0x14000aaac  lea     r8, [rbx+8]
0x14000aab0  mov     rax, rbx
0x14000aab3  neg     rax
0x14000aab6  mov     r9, [rcx]
0x14000aab9  sbb     rdx, rdx
0x14000aabc  and     rdx, r8
0x14000aabf  mov     rax, [r9+40h]
0x14000aac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aac8  mov     edi, eax
0x14000aaca  test    eax, eax
0x14000aacc  js      short loc_14000AB13
0x14000aace  mov     rax, [rsi]
0x14000aad1  lea     rdx, [rsp+38h+arg_0]
0x14000aad6  mov     rcx, rsi
0x14000aad9  mov     rax, [rax+60h]
0x14000aadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aae2  mov     edi, eax
0x14000aae4  test    eax, eax
0x14000aae6  js      short loc_14000AB13
0x14000aae8  mov     rcx, [r15]
0x14000aaeb  mov     rdx, [rsp+38h+arg_0]
0x14000aaf0  mov     rax, [rcx]
0x14000aaf3  mov     rax, [rax+50h]
0x14000aaf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aafc  mov     rcx, [rsp+38h+arg_0]
0x14000ab01  mov     edi, eax
0x14000ab03  mov     rax, [rcx]
0x14000ab06  mov     rax, [rax+10h]
0x14000ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab0f  test    edi, edi
0x14000ab11  jns     short loc_14000AB24
0x14000ab13  mov     rax, [rbx]
0x14000ab16  mov     rcx, rbx
0x14000ab19  mov     rax, [rax+10h]
0x14000ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab22  jmp     short loc_14000AB30
0x14000ab24  mov     [r14], rbx
0x14000ab27  xor     edi, edi
0x14000ab29  jmp     short loc_14000AB30
0x14000ab2b  mov     edi, 8007000Eh
0x14000ab30  mov     eax, edi
0x14000ab32  jmp     short loc_14000AB39
0x14000ab34  mov     eax, 80004003h
0x14000ab39  mov     rbx, [rsp+38h+arg_8]
0x14000ab3e  mov     rsi, [rsp+38h+arg_10]
0x14000ab43  add     rsp, 20h
0x14000ab47  pop     r15
0x14000ab49  pop     r14
0x14000ab4b  pop     rdi
0x14000ab4c  retn
```
