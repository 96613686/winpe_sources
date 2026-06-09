# UWFUpdateAgent::ApplyOnce(int *)

- ea: `0x18000399c`
- end: `0x180003c63`
- name: `?ApplyOnce@UWFUpdateAgent@@AEAAJPEAH@Z`
- size: `711`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180003130`

## callees

- `0x180001536`
- `0x180002a20`
- `0x18000399c`
- `0x1800045d0`
- `0x18000490c`
- `0x180004a70`
- `0x180006010`

## string_xrefs

- `0x180003b8c`: `Found %d updates`
- `0x180003a9d`: `(IsInstalled = 0) and (IsHidden = 0)`
- `0x180003ab9`: `Search for available updates failed`
- `0x180003adc`: `get_Updates failed`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::ApplyOnce(UWFUpdateAgent *this, int *a2)
{
  __int64 v3; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ebx
  const wchar_t *v11; // r9
  struct IUpdateCollection *v12; // rcx
  UWFUpdateAgent *v13; // rcx
  int v14; // eax
  int *v15; // rax
  int v17; // [rsp+20h] [rbp-10h]
  struct IUpdateCollection *v18; // [rsp+60h] [rbp+30h] BYREF
  struct IUpdateCollection *v19; // [rsp+68h] [rbp+38h] BYREF
  __int64 v20; // [rsp+70h] [rbp+40h] BYREF
  __int64 v21; // [rsp+78h] [rbp+48h] BYREF

  v18 = 0;
  v3 = *((_QWORD *)this + 2);
  v19 = 0;
  *a2 = 0;
  if ( v3 )
  {
    v5 = *(void **)(v3 + 24);
    if ( v5 )
      operator delete(v5);
    v6 = *(void **)(*((_QWORD *)this + 2) + 32LL);
    if ( v6 )
      operator delete(v6);
    v7 = *((_QWORD *)this + 2);
    *(_OWORD *)v7 = 0;
    *(_OWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 32) = 0;
    *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 2) + 32LL) = 0;
  }
  v8 = *((_QWORD *)this + 1);
  v20 = 0;
  v21 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 96LL))(v8, &v20);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 168LL))(v20, 0xFFFFFFFFLL);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 112LL))(v20, 0);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v20 + 152LL))(
               v20,
               L"(IsInstalled = 0) and (IsHidden = 0)",
               &v21);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v21 + 72LL))(v21, &v18);
          v10 = v9;
          if ( v9 >= 0 )
            goto LABEL_18;
          v11 = L"get_Updates failed";
        }
        else
        {
          v11 = L"Search for available updates failed";
        }
      }
      else
      {
        v11 = L"Searcher put_ServerSelection failed";
      }
    }
    else
    {
      v11 = L"Searcher put_Online failed";
    }
  }
  else
  {
    v11 = L"Search error";
  }
  UwfServicingLog(1, 1, (unsigned int)v9, v11);
LABEL_18:
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v10 < 0 )
    goto LABEL_36;
  v12 = v18;
  if ( v18 )
  {
    v10 = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD))v18->lpVtbl->get_Count)(
            v18,
            *((_QWORD *)this + 2));
    if ( v10 < 0 )
      goto LABEL_36;
    v10 = UWFUpdateAgent::filter(v13, v18, &v19);
    if ( v10 < 0 )
      goto LABEL_36;
    if ( !v19 )
      goto LABEL_39;
    v10 = ((__int64 (__fastcall *)(struct IUpdateCollection *, __int64))v19->lpVtbl->get_Count)(
            v19,
            *((_QWORD *)this + 2) + 4LL);
    if ( v10 < 0 )
      goto LABEL_36;
    v17 = *(_DWORD *)(*((_QWORD *)this + 2) + 4LL);
    UwfServicingLog(1, 0, 0, L"Found %d updates", v17);
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 4LL) )
    {
      v14 = UWFUpdateAgent::download(this, v19);
      v10 = v14;
      if ( v14 < 0 )
      {
        UwfServicingLog(1, 1, (unsigned int)v14, L"Failed to download");
LABEL_36:
        v12 = v18;
        goto LABEL_37;
      }
      v10 = UWFUpdateAgent::install(this, v19);
      if ( v10 < 0 )
        goto LABEL_36;
    }
    v15 = (int *)*((_QWORD *)this + 2);
    if ( !v15[5] && !v15[4] && v15[3] > 0 )
      *a2 = 1;
    goto LABEL_36;
  }
LABEL_37:
  if ( !v19 )
    goto LABEL_40;
  ((void (__fastcall *)(struct IUpdateCollection *))v19->lpVtbl->Clear)(v19);
  ((void (__fastcall *)(struct IUpdateCollection *))v19->lpVtbl->Release)(v19);
LABEL_39:
  v12 = v18;
LABEL_40:
  if ( v12 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v12->lpVtbl->Clear)(v12);
    ((void (__fastcall *)(struct IUpdateCollection *))v18->lpVtbl->Release)(v18);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000399c  push    rbp
0x18000399e  push    rbx
0x18000399f  push    rsi
0x1800039a0  push    rdi
0x1800039a1  push    r15
0x1800039a3  mov     rbp, rsp
0x1800039a6  sub     rsp, 30h
0x1800039aa  mov     rdi, rcx
0x1800039ad  mov     [rbp+arg_0], 0
0x1800039b5  mov     rcx, [rcx+10h]
0x1800039b9  mov     rsi, rdx
0x1800039bc  mov     [rbp+arg_8], 0
0x1800039c4  mov     dword ptr [rdx], 0
0x1800039ca  test    rcx, rcx
0x1800039cd  jz      short loc_180003A13
0x1800039cf  mov     rcx, [rcx+18h]; void *
0x1800039d3  test    rcx, rcx
0x1800039d6  jz      short loc_1800039DD
0x1800039d8  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800039dd  mov     rax, [rdi+10h]
0x1800039e1  mov     rcx, [rax+20h]; void *
0x1800039e5  test    rcx, rcx
0x1800039e8  jz      short loc_1800039EF
0x1800039ea  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800039ef  mov     rax, [rdi+10h]
0x1800039f3  xor     ecx, ecx
0x1800039f5  xorps   xmm0, xmm0
0x1800039f8  movups  xmmword ptr [rax], xmm0
0x1800039fb  movups  xmmword ptr [rax+10h], xmm0
0x1800039ff  mov     [rax+20h], rcx
0x180003a03  mov     rax, [rdi+10h]
0x180003a07  mov     [rax+18h], rcx
0x180003a0b  mov     rax, [rdi+10h]
0x180003a0f  mov     [rax+20h], rcx
0x180003a13  mov     rcx, [rdi+8]
0x180003a17  lea     rdx, [rbp+arg_10]
0x180003a1b  mov     [rbp+arg_10], 0
0x180003a23  mov     [rbp+arg_18], 0
0x180003a2b  mov     rax, [rcx]
0x180003a2e  mov     rax, [rax+60h]
0x180003a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a37  mov     ebx, eax
0x180003a39  mov     r15d, 1
0x180003a3f  test    eax, eax
0x180003a41  jns     short loc_180003A4F
0x180003a43  lea     r9, aSearchError; "Search error"
0x180003a4a  jmp     loc_180003AE3
0x180003a4f  mov     rcx, [rbp+arg_10]
0x180003a53  or      edx, 0FFFFFFFFh
0x180003a56  mov     rax, [rcx]
0x180003a59  mov     rax, [rax+0A8h]
0x180003a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a65  mov     ebx, eax
0x180003a67  test    eax, eax
0x180003a69  jns     short loc_180003A74
0x180003a6b  lea     r9, aSearcherPutOnl; "Searcher put_Online failed"
0x180003a72  jmp     short loc_180003AE3
0x180003a74  mov     rcx, [rbp+arg_10]
0x180003a78  xor     edx, edx
0x180003a7a  mov     rax, [rcx]
0x180003a7d  mov     rax, [rax+70h]
0x180003a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a86  mov     ebx, eax
0x180003a88  test    eax, eax
0x180003a8a  jns     short loc_180003A95
0x180003a8c  lea     r9, aSearcherPutSer; "Searcher put_ServerSelection failed"
0x180003a93  jmp     short loc_180003AE3
0x180003a95  mov     rcx, [rbp+arg_10]
0x180003a99  lea     r8, [rbp+arg_18]
0x180003a9d  lea     rdx, aIsinstalled0An; "(IsInstalled = 0) and (IsHidden = 0)"
0x180003aa4  mov     rax, [rcx]
0x180003aa7  mov     rax, [rax+98h]
0x180003aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab3  mov     ebx, eax
0x180003ab5  test    eax, eax
0x180003ab7  jns     short loc_180003AC2
0x180003ab9  lea     r9, aSearchForAvail; "Search for available updates failed"
0x180003ac0  jmp     short loc_180003AE3
0x180003ac2  mov     rcx, [rbp+arg_18]
0x180003ac6  lea     rdx, [rbp+arg_0]
0x180003aca  mov     rax, [rcx]
0x180003acd  mov     rax, [rax+48h]
0x180003ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad6  mov     ebx, eax
0x180003ad8  test    eax, eax
0x180003ada  jns     short loc_180003AF1
0x180003adc  lea     r9, aGetUpdatesFail; "get_Updates failed"
0x180003ae3  mov     r8d, eax
0x180003ae6  mov     edx, r15d
0x180003ae9  mov     ecx, r15d
0x180003aec  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003af1  mov     rcx, [rbp+arg_18]
0x180003af5  test    rcx, rcx
0x180003af8  jz      short loc_180003B06
0x180003afa  mov     rax, [rcx]
0x180003afd  mov     rax, [rax+10h]
0x180003b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b06  mov     rcx, [rbp+arg_10]
0x180003b0a  test    rcx, rcx
0x180003b0d  jz      short loc_180003B1B
0x180003b0f  mov     rax, [rcx]
0x180003b12  mov     rax, [rax+10h]
0x180003b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1b  test    ebx, ebx
0x180003b1d  js      loc_180003C05
0x180003b23  mov     rcx, [rbp+arg_0]
0x180003b27  test    rcx, rcx
0x180003b2a  jz      loc_180003C09
0x180003b30  mov     rax, [rcx]
0x180003b33  mov     rdx, [rdi+10h]
0x180003b37  mov     rax, [rax+50h]
0x180003b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b40  mov     ebx, eax
0x180003b42  test    eax, eax
0x180003b44  js      loc_180003C05
0x180003b4a  mov     rdx, [rbp+arg_0]; struct IUpdateCollection *
0x180003b4e  lea     r8, [rbp+arg_8]; struct IUpdateCollection **
0x180003b52  call    ?filter@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@PEAPEAU2@@Z; UWFUpdateAgent::filter(IUpdateCollection *,IUpdateCollection * *)
0x180003b57  mov     ebx, eax
0x180003b59  test    eax, eax
0x180003b5b  js      loc_180003C05
0x180003b61  mov     rcx, [rbp+arg_8]
0x180003b65  test    rcx, rcx
0x180003b68  jz      loc_180003C31
0x180003b6e  mov     rax, [rcx]
0x180003b71  mov     rdx, [rdi+10h]
0x180003b75  add     rdx, 4
0x180003b79  mov     rax, [rax+50h]
0x180003b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b82  mov     ebx, eax
0x180003b84  test    eax, eax
0x180003b86  js      short loc_180003C05
0x180003b88  mov     rax, [rdi+10h]
0x180003b8c  lea     r9, aFoundDUpdates; "Found %d updates"
0x180003b93  xor     r8d, r8d
0x180003b96  xor     edx, edx
0x180003b98  mov     ecx, [rax+4]
0x180003b9b  mov     [rsp+30h+var_10], ecx
0x180003b9f  mov     ecx, r15d
0x180003ba2  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003ba7  mov     rax, [rdi+10h]
0x180003bab  cmp     dword ptr [rax+4], 0
0x180003baf  jz      short loc_180003BEC
0x180003bb1  mov     rdx, [rbp+arg_8]; struct IUpdateCollection *
0x180003bb5  mov     rcx, rdi; this
0x180003bb8  call    ?download@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@@Z; UWFUpdateAgent::download(IUpdateCollection *)
0x180003bbd  mov     ebx, eax
0x180003bbf  test    eax, eax
0x180003bc1  jns     short loc_180003BDA
0x180003bc3  lea     r9, aFailedToDownlo; "Failed to download"
0x180003bca  mov     r8d, eax
0x180003bcd  mov     edx, r15d
0x180003bd0  mov     ecx, r15d
0x180003bd3  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003bd8  jmp     short loc_180003C05
0x180003bda  mov     rdx, [rbp+arg_8]; struct IUpdateCollection *
0x180003bde  mov     rcx, rdi; this
0x180003be1  call    ?install@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@@Z; UWFUpdateAgent::install(IUpdateCollection *)
0x180003be6  mov     ebx, eax
0x180003be8  test    eax, eax
0x180003bea  js      short loc_180003C05
0x180003bec  mov     rax, [rdi+10h]
0x180003bf0  cmp     dword ptr [rax+14h], 0
0x180003bf4  jnz     short loc_180003C05
0x180003bf6  cmp     dword ptr [rax+10h], 0
0x180003bfa  jnz     short loc_180003C05
0x180003bfc  cmp     dword ptr [rax+0Ch], 0
0x180003c00  jle     short loc_180003C05
0x180003c02  mov     [rsi], r15d
0x180003c05  mov     rcx, [rbp+arg_0]
0x180003c09  mov     rdx, [rbp+arg_8]
0x180003c0d  test    rdx, rdx
0x180003c10  jz      short loc_180003C35
0x180003c12  mov     rax, [rdx]
0x180003c15  mov     rcx, rdx
0x180003c18  mov     rax, [rax+68h]
0x180003c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c21  mov     rcx, [rbp+arg_8]
0x180003c25  mov     rax, [rcx]
0x180003c28  mov     rax, [rax+10h]
0x180003c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c31  mov     rcx, [rbp+arg_0]
0x180003c35  test    rcx, rcx
0x180003c38  jz      short loc_180003C56
0x180003c3a  mov     rax, [rcx]
0x180003c3d  mov     rax, [rax+68h]
0x180003c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c46  mov     rcx, [rbp+arg_0]
0x180003c4a  mov     rax, [rcx]
0x180003c4d  mov     rax, [rax+10h]
0x180003c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c56  mov     eax, ebx
0x180003c58  add     rsp, 30h
0x180003c5c  pop     r15
0x180003c5e  pop     rdi
0x180003c5f  pop     rsi
0x180003c60  pop     rbx
0x180003c61  pop     rbp
0x180003c62  retn
```
