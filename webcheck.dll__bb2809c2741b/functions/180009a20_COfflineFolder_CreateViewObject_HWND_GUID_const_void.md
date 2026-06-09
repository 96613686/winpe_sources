# COfflineFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180009a20`
- end: `0x180009b98`
- name: `?CreateViewObject@COfflineFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `376`
- prototype: `int(COfflineFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009670`
- `0x180009a20`
- `0x18001ba08`
- `0x18002a010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderViewEx` at `0x180009a99`
- `SHELL32!__imp_SHCreateShellFolderViewEx` at `0x180009a99`

## pseudocode

```c
__int64 __fastcall COfflineFolder::CreateViewObject(
        COfflineFolder *this,
        HWND a2,
        const struct _GUID *a3,
        IShellView **a4)
{
  __int64 v7; // rax
  int v9; // ebx
  __int64 v10; // rax
  COfflineFolder *v11; // rax
  COfflineFolder *v12; // rax
  COfflineFolder *v13; // rsi
  __int64 v14; // rax
  CSFV pcsfv; // [rsp+20h] [rbp-78h] BYREF

  *a4 = 0;
  v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( !v7 )
  {
    pcsfv.pidl = (LPCITEMIDLIST)*((_QWORD *)this + 4);
    *(_QWORD *)&pcsfv.cbSize = 56;
    pcsfv.pfnCallback = OfflineFolderView_ViewCallback;
    *(_QWORD *)&pcsfv.lEvents = 12295;
    *(_QWORD *)&pcsfv.fvm = 0;
    pcsfv.pshf = (IShellFolder *)this;
    pcsfv.psvOuter = 0;
    return (unsigned int)SHCreateShellFolderViewEx(&pcsfv, a4);
  }
  v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v10 )
  {
    v11 = (COfflineFolder *)operator new(0x30u);
    if ( v11 )
    {
      v12 = COfflineFolder::COfflineFolder(v11);
      v13 = v12;
      if ( v12 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v12 + 1) + 32LL))(
               (__int64)v12 + 8,
               *((_QWORD *)this + 4));
        if ( v9 < 0 )
        {
LABEL_18:
          (*(void (__fastcall **)(COfflineFolder *))(*(_QWORD *)v13 + 16LL))(v13);
          return (unsigned int)v9;
        }
LABEL_17:
        v9 = (**(__int64 (__fastcall ***)(COfflineFolder *, const struct _GUID *, IShellView **))v13)(v13, a3, a4);
        goto LABEL_18;
      }
    }
    return (unsigned int)-2147024882;
  }
  v9 = -2147467262;
  v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
    v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
  if ( !v14 )
  {
    v13 = (COfflineFolder *)operator new(0x30u);
    if ( v13 )
    {
      *((_QWORD *)v13 + 2) = 1;
      *(_QWORD *)v13 = &COfflineDropTarget::`vftable';
      *((_QWORD *)v13 + 5) = a2;
      *((_QWORD *)v13 + 1) = 0;
      *((_QWORD *)v13 + 3) = 0;
      *((_QWORD *)v13 + 4) = 0;
      _InterlockedIncrement((volatile signed __int32 *)&g_cObj);
      goto LABEL_17;
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009a20  push    rbx
0x180009a22  push    rbp
0x180009a23  push    rsi
0x180009a24  push    rdi
0x180009a25  push    r14
0x180009a27  push    r15
0x180009a29  sub     rsp, 68h
0x180009a2d  xor     r15d, r15d
0x180009a30  mov     r14, r9
0x180009a33  mov     [r9], r15
0x180009a36  mov     rdi, r8
0x180009a39  mov     rax, [r8]
0x180009a3c  mov     rbp, rdx
0x180009a3f  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180009a46  mov     rbx, rcx
0x180009a49  jnz     short loc_180009A56
0x180009a4b  mov     rax, [r8+8]
0x180009a4f  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180009a56  test    rax, rax
0x180009a59  jnz     short loc_180009AA6
0x180009a5b  mov     rax, [rcx+20h]
0x180009a5f  mov     rdx, r14; ppsv
0x180009a62  mov     [rsp+98h+pcsfv.pidl], rax
0x180009a67  lea     rcx, [rsp+98h+pcsfv]; pcsfv
0x180009a6c  lea     rax, ?OfflineFolderView_ViewCallback@@YAJPEAUIShellView@@PEAUIShellFolder@@PEAUHWND__@@I_K_J@Z; OfflineFolderView_ViewCallback(IShellView *,IShellFolder *,HWND__ *,uint,unsigned __int64,__int64)
0x180009a73  mov     qword ptr [rsp+98h+pcsfv.cbSize], 38h ; '8'
0x180009a7c  mov     [rsp+98h+pcsfv.pfnCallback], rax
0x180009a81  mov     qword ptr [rsp+98h+pcsfv.lEvents], 3007h
0x180009a8a  mov     qword ptr [rsp+98h+pcsfv.fvm], r15
0x180009a8f  mov     [rsp+98h+pcsfv.pshf], rbx
0x180009a94  mov     [rsp+98h+pcsfv.psvOuter], r15
0x180009a99  call    cs:__imp_SHCreateShellFolderViewEx
0x180009a9f  mov     ebx, eax
0x180009aa1  jmp     loc_180009B89
0x180009aa6  mov     rax, [r8]
0x180009aa9  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180009ab0  jnz     short loc_180009ABD
0x180009ab2  mov     rax, [r8+8]
0x180009ab6  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180009abd  test    rax, rax
0x180009ac0  jnz     short loc_180009B03
0x180009ac2  lea     ecx, [rax+30h]; dwBytes
0x180009ac5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009aca  test    rax, rax
0x180009acd  jz      loc_180009B84
0x180009ad3  mov     rcx, rax; this
0x180009ad6  call    ??0COfflineFolder@@QEAA@XZ; COfflineFolder::COfflineFolder(void)
0x180009adb  mov     rsi, rax
0x180009ade  test    rax, rax
0x180009ae1  jz      loc_180009B84
0x180009ae7  lea     rcx, [rax+8]
0x180009aeb  mov     rdx, [rcx]
0x180009aee  mov     rax, [rdx+20h]
0x180009af2  mov     rdx, [rbx+20h]
0x180009af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009afb  mov     ebx, eax
0x180009afd  test    eax, eax
0x180009aff  js      short loc_180009B73
0x180009b01  jmp     short loc_180009B5D
0x180009b03  mov     rax, [r8]
0x180009b06  mov     ebx, 80004002h
0x180009b0b  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180009b12  jnz     short loc_180009B1F
0x180009b14  mov     rax, [r8+8]
0x180009b18  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x180009b1f  test    rax, rax
0x180009b22  jnz     short loc_180009B89
0x180009b24  lea     ecx, [rax+30h]; dwBytes
0x180009b27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b2c  mov     rsi, rax
0x180009b2f  test    rax, rax
0x180009b32  jz      short loc_180009B84
0x180009b34  lea     rax, ??_7COfflineDropTarget@@6B@; const COfflineDropTarget::`vftable'
0x180009b3b  mov     qword ptr [rsi+10h], 1
0x180009b43  mov     [rsi], rax
0x180009b46  mov     [rsi+28h], rbp
0x180009b4a  mov     [rsi+8], r15
0x180009b4e  mov     [rsi+18h], r15
0x180009b52  mov     [rsi+20h], r15
0x180009b56  lock inc cs:?g_cObj@@3KA; ulong g_cObj
0x180009b5d  mov     rax, [rsi]
0x180009b60  mov     r8, r14
0x180009b63  mov     rdx, rdi
0x180009b66  mov     rcx, rsi
0x180009b69  mov     rax, [rax]
0x180009b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b71  mov     ebx, eax
0x180009b73  mov     rax, [rsi]
0x180009b76  mov     rcx, rsi
0x180009b79  mov     rax, [rax+10h]
0x180009b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b82  jmp     short loc_180009B89
0x180009b84  mov     ebx, 8007000Eh
0x180009b89  mov     eax, ebx
0x180009b8b  add     rsp, 68h
0x180009b8f  pop     r15
0x180009b91  pop     r14
0x180009b93  pop     rdi
0x180009b94  pop     rsi
0x180009b95  pop     rbp
0x180009b96  pop     rbx
0x180009b97  retn
```
