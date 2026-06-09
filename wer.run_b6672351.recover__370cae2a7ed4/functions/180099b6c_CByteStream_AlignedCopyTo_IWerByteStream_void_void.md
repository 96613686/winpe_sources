# CByteStream::AlignedCopyTo(IWerByteStream *,void *,void *)

- ea: `0x180099b6c`
- end: `0x180099e74`
- name: `?AlignedCopyTo@CByteStream@@QEAAJPEAUIWerByteStream@@PEAX1@Z`
- size: `776`
- prototype: `__int64 __fastcall(CByteStream *__hidden this, struct IWerByteStream *, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180083840`

## callees

- `0x180004c64`
- `0x180020680`
- `0x18003de9c`
- `0x180053300`
- `0x180053d3c`
- `0x180099b6c`
- `0x1800af010`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099c4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099c4a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180099dfe`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180099dfe`

## pseudocode

```c
__int64 __fastcall CByteStream::AlignedCopyTo(CByteStream *this, struct IWerByteStream *a2, void *a3, void *a4)
{
  unsigned int v7; // edi
  __int64 (__fastcall **v9)(CByteStream *, _BYTE *, __int64, unsigned int *, void *); // rax
  signed int v10; // ebx
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 i; // r14
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  signed int LastError; // eax
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-CCh] BYREF
  __int64 FileInformation; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  v9 = *(__int64 (__fastcall ***)(CByteStream *, _BYTE *, __int64, unsigned int *, void *))this;
  FileInformation = 0;
  v10 = ((__int64 (__fastcall *)(CByteStream *, _QWORD, _QWORD, _QWORD))v9[2])(this, 0, 0, 0);
  if ( v10 >= 0 )
  {
    for ( i = 0; i < (*(__int64 (__fastcall **)(CByteStream *))(*(_QWORD *)this + 32LL))(this); i += v19 )
    {
      if ( a3 && !WaitForSingleObject(a3, 0) )
      {
        v10 = -2147467260;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v12 = 15;
          v13 = 2147500036LL;
          goto LABEL_6;
        }
        return (unsigned int)v10;
      }
      v10 = (**(__int64 (__fastcall ***)(CByteStream *, _BYTE *, __int64, unsigned int *, void *))this)(
              this,
              v26,
              4096,
              &v23,
              a3);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 16;
          goto LABEL_5;
        }
        return (unsigned int)v10;
      }
      v15 = v23;
      if ( v23 < 0x1000 )
      {
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids);
          return (unsigned int)-2147024569;
        }
        v7 = 4096 - v23;
        memset_0(&v26[v23], 0, 4096 - v23);
        v15 = 4096;
      }
      v10 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _BYTE *, _QWORD, unsigned int *, void *))(*(_QWORD *)a2 + 8LL))(
              a2,
              v26,
              v15,
              &v24,
              a3);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 18;
          goto LABEL_5;
        }
        return (unsigned int)v10;
      }
      v19 = v24;
      if ( v23 != v24 && !v7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18);
        v19 = v24;
      }
    }
    if ( !v7 )
      return 0;
    v20 = *(_QWORD *)this;
    FileInformation = 0;
    FileInformation = (*(__int64 (__fastcall **)(CByteStream *))(v20 + 32))(this);
    if ( SetFileInformationByHandle(a4, FileEndOfFileInfo, &FileInformation, 8u) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 19;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 14;
LABEL_5:
      v13 = (unsigned int)v10;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids, v13);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180099b6c  push    rbp
0x180099b6e  push    rbx
0x180099b6f  push    rsi
0x180099b70  push    rdi
0x180099b71  push    r12
0x180099b73  push    r13
0x180099b75  push    r14
0x180099b77  push    r15
0x180099b79  lea     rbp, [rsp-0F58h]
0x180099b81  mov     eax, 1058h
0x180099b86  call    _alloca_probe
0x180099b8b  sub     rsp, rax
0x180099b8e  mov     rax, cs:__security_cookie
0x180099b95  xor     rax, rsp
0x180099b98  mov     [rbp+0F90h+var_50], rax
0x180099b9f  mov     r15, r8
0x180099ba2  mov     r12, rdx
0x180099ba5  mov     rsi, rcx
0x180099ba8  xor     edi, edi
0x180099baa  xor     edx, edx; Val
0x180099bac  mov     [rsp+1090h+var_1060], edi
0x180099bb0  mov     r8d, 1000h; Size
0x180099bb6  mov     [rsp+1090h+var_105C], edi
0x180099bba  lea     rcx, [rsp+1090h+var_1050]; void *
0x180099bbf  mov     r13, r9
0x180099bc2  call    memset_0
0x180099bc7  mov     rax, [rsi]
0x180099bca  xor     r9d, r9d
0x180099bcd  xor     r8d, r8d
0x180099bd0  mov     [rsp+1090h+FileInformation], rdi
0x180099bd5  xor     edx, edx
0x180099bd7  mov     rcx, rsi
0x180099bda  mov     rax, [rax+10h]
0x180099bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099be3  mov     ebx, eax
0x180099be5  test    eax, eax
0x180099be7  jns     short loc_180099C25
0x180099be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bf0  lea     rax, WPP_GLOBAL_Control
0x180099bf7  cmp     rcx, rax
0x180099bfa  jz      loc_180099E4E
0x180099c00  test    byte ptr [rcx+1Ch], 1
0x180099c04  jz      loc_180099E4E
0x180099c0a  lea     edx, [rdi+0Eh]
0x180099c0d  mov     r9d, ebx
0x180099c10  mov     rcx, [rcx+10h]
0x180099c14  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x180099c1b  call    WPP_SF_d
0x180099c20  jmp     loc_180099E4E
0x180099c25  xor     r14d, r14d
0x180099c28  mov     rax, [rsi]
0x180099c2b  mov     rcx, rsi
0x180099c2e  mov     rax, [rax+20h]
0x180099c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c37  cmp     r14, rax
0x180099c3a  jnb     loc_180099DCB
0x180099c40  test    r15, r15
0x180099c43  jz      short loc_180099C5E
0x180099c45  xor     edx, edx; dwMilliseconds
0x180099c47  mov     rcx, r15; hHandle
0x180099c4a  call    cs:__imp_WaitForSingleObject
0x180099c51  nop     dword ptr [rax+rax+00h]
0x180099c56  test    eax, eax
0x180099c58  jz      loc_180099D07
0x180099c5e  mov     rax, [rsi]
0x180099c61  lea     r9, [rsp+1090h+var_1060]
0x180099c66  mov     r8d, 1000h
0x180099c6c  mov     [rsp+1090h+var_1070], r15
0x180099c71  lea     rdx, [rsp+1090h+var_1050]
0x180099c76  mov     rcx, rsi
0x180099c79  mov     rax, [rax]
0x180099c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c81  mov     ebx, eax
0x180099c83  test    eax, eax
0x180099c85  js      loc_180099DA0
0x180099c8b  mov     ecx, [rsp+1090h+var_1060]
0x180099c8f  mov     ebx, 1000h
0x180099c94  cmp     ecx, ebx
0x180099c96  jnb     short loc_180099CBC
0x180099c98  test    edi, edi
0x180099c9a  jnz     loc_180099D3D
0x180099ca0  mov     eax, ebx
0x180099ca2  xor     edx, edx; Val
0x180099ca4  sub     eax, ecx
0x180099ca6  mov     edi, eax
0x180099ca8  mov     r8d, eax; Size
0x180099cab  mov     eax, ecx
0x180099cad  lea     rcx, [rsp+1090h+var_1050]
0x180099cb2  add     rcx, rax; void *
0x180099cb5  call    memset_0
0x180099cba  mov     ecx, ebx
0x180099cbc  mov     rax, [r12]
0x180099cc0  lea     r9, [rsp+1090h+var_105C]
0x180099cc5  mov     r8d, ecx
0x180099cc8  mov     [rsp+1090h+var_1070], r15
0x180099ccd  lea     rdx, [rsp+1090h+var_1050]
0x180099cd2  mov     rcx, r12
0x180099cd5  mov     rax, [rax+8]
0x180099cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cde  mov     ebx, eax
0x180099ce0  test    eax, eax
0x180099ce2  js      loc_180099D75
0x180099ce8  mov     eax, [rsp+1090h+var_105C]
0x180099cec  cmp     [rsp+1090h+var_1060], eax
0x180099cf0  jz      short loc_180099CFF
0x180099cf2  test    edi, edi
0x180099cf4  jnz     short loc_180099CFF
0x180099cf6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180099cfb  mov     eax, [rsp+1090h+var_105C]
0x180099cff  add     r14, rax
0x180099d02  jmp     loc_180099C28
0x180099d07  mov     ebx, 80004004h
0x180099d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d13  lea     rax, WPP_GLOBAL_Control
0x180099d1a  cmp     rcx, rax
0x180099d1d  jz      loc_180099E4E
0x180099d23  test    byte ptr [rcx+1Ch], 4
0x180099d27  jz      loc_180099E4E
0x180099d2d  mov     edx, 0Fh
0x180099d32  mov     r9d, 80004004h
0x180099d38  jmp     loc_180099C10
0x180099d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d44  lea     rax, WPP_GLOBAL_Control
0x180099d4b  cmp     rcx, rax
0x180099d4e  jz      short loc_180099D6B
0x180099d50  test    byte ptr [rcx+1Ch], 1
0x180099d54  jz      short loc_180099D6B
0x180099d56  mov     rcx, [rcx+10h]
0x180099d5a  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x180099d61  mov     edx, 11h
0x180099d66  call    WPP_SF_
0x180099d6b  mov     ebx, 80070147h
0x180099d70  jmp     loc_180099E4E
0x180099d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d7c  lea     rax, WPP_GLOBAL_Control
0x180099d83  cmp     rcx, rax
0x180099d86  jz      loc_180099E4E
0x180099d8c  test    byte ptr [rcx+1Ch], 1
0x180099d90  jz      loc_180099E4E
0x180099d96  mov     edx, 12h
0x180099d9b  jmp     loc_180099C0D
0x180099da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180099da7  lea     rax, WPP_GLOBAL_Control
0x180099dae  cmp     rcx, rax
0x180099db1  jz      loc_180099E4E
0x180099db7  test    byte ptr [rcx+1Ch], 1
0x180099dbb  jz      loc_180099E4E
0x180099dc1  mov     edx, 10h
0x180099dc6  jmp     loc_180099C0D
0x180099dcb  test    edi, edi
0x180099dcd  jz      short loc_180099E4C
0x180099dcf  mov     rax, [rsi]
0x180099dd2  mov     rcx, rsi
0x180099dd5  mov     [rsp+1090h+FileInformation], 0
0x180099dde  mov     rax, [rax+20h]
0x180099de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099de7  mov     r9d, 8; dwBufferSize
0x180099ded  mov     [rsp+1090h+FileInformation], rax
0x180099df2  lea     r8, [rsp+1090h+FileInformation]; lpFileInformation
0x180099df7  mov     rcx, r13; hFile
0x180099dfa  lea     edx, [r9-2]; FileInformationClass
0x180099dfe  call    cs:__imp_SetFileInformationByHandle
0x180099e05  nop     dword ptr [rax+rax+00h]
0x180099e0a  test    eax, eax
0x180099e0c  jnz     short loc_180099E4C
0x180099e0e  call    cs:__imp_GetLastError
0x180099e15  nop     dword ptr [rax+rax+00h]
0x180099e1a  mov     ebx, eax
0x180099e1c  test    eax, eax
0x180099e1e  jle     short loc_180099E29
0x180099e20  movzx   ebx, ax
0x180099e23  or      ebx, 80070000h
0x180099e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e30  lea     rax, WPP_GLOBAL_Control
0x180099e37  cmp     rcx, rax
0x180099e3a  jz      short loc_180099E4E
0x180099e3c  test    byte ptr [rcx+1Ch], 1
0x180099e40  jz      short loc_180099E4E
0x180099e42  mov     edx, 13h
0x180099e47  jmp     loc_180099C0D
0x180099e4c  xor     ebx, ebx
0x180099e4e  mov     eax, ebx
0x180099e50  mov     rcx, [rbp+0F90h+var_50]
0x180099e57  xor     rcx, rsp; StackCookie
0x180099e5a  call    __security_check_cookie
0x180099e5f  add     rsp, 1058h
0x180099e66  pop     r15
0x180099e68  pop     r14
0x180099e6a  pop     r13
0x180099e6c  pop     r12
0x180099e6e  pop     rdi
0x180099e6f  pop     rsi
0x180099e70  pop     rbx
0x180099e71  pop     rbp
0x180099e72  retn
```
