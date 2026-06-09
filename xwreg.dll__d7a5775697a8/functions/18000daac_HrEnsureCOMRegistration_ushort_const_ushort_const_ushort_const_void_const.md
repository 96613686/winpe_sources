# HrEnsureCOMRegistration(ushort * const,ushort * const,ushort * * const,void * const)

- ea: `0x18000daac`
- end: `0x18000dd35`
- name: `?HrEnsureCOMRegistration@@YAJQEAG0QEAPEAGQEAX@Z`
- size: `649`
- prototype: `__int64 __fastcall(unsigned __int16 *const, LPCWSTR lpSrc, unsigned __int16 **const, void *const)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007b28`
- `0x18000c5c8`

## callees

- `0x180007820`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ace0`
- `0x18000daac`
- `0x18000e8bc`
- `0x18000ee04`
- `0x18000f010`
- `0x18000f484`
- `0x18000f7c4`
- `0x18000fa80`
- `0x18001236c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbe1`

## string_xrefs

- `0x18000db11`: `xwizards.dll`
- `0x18000db76`: `xwizards.dll`
- `0x18000dc41`: `xwizards.dll`

## pseudocode

```c
__int64 __fastcall HrEnsureCOMRegistration(
        unsigned __int16 *const a1,
        LPCWSTR lpSrc,
        unsigned __int16 **const a3,
        void *const a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rbx
  int FullNonHardCodedPath; // eax
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r9
  __int64 v14; // rax
  __int64 v15; // r14
  unsigned __int16 *v16; // rax
  const unsigned __int16 *v18; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Src[264]; // [rsp+40h] [rbp-C0h] BYREF

  pv = 0;
  if ( a3 )
    *a3 = 0;
  v8 = HrVerifyCOMRegistration(a1, (unsigned __int16 **const)&pv);
  v9 = v8;
  if ( !v8 )
  {
    v10 = (unsigned __int16 *)pv;
    if ( wcsistr((const unsigned __int16 *)pv, L"xwizards.dll") )
      HrWriteManifestCOMEntry(a1, a4);
    if ( a3 )
      *a3 = v10;
    else
      CoTaskMemFree(v10);
    v9 = 1;
    goto LABEL_34;
  }
  if ( v8 != 1 )
  {
LABEL_34:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
    return v9;
  }
  if ( !lpSrc )
  {
    v9 = -2147221164;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (_DWORD)a1,
        84);
    goto LABEL_34;
  }
  FullNonHardCodedPath = HrMakeFullNonHardCodedPath(lpSrc, Src);
  v9 = FullNonHardCodedPath;
  if ( FullNonHardCodedPath >= 0 )
  {
    if ( wcsistr(Src, L"xwizards.dll") )
    {
      v9 = HrRegisterCOMServer(Src, a1, v12, v13, v18);
      HrWriteManifestCOMEntry(a1, a4);
    }
    else
    {
      v9 = HrRegisterOrUnregisterWithCOM(Src, 1);
    }
    if ( (v9 & 0x80000000) == 0 && a3 )
    {
      v14 = -1;
      do
        ++v14;
      while ( Src[v14] );
      v15 = (unsigned int)(v14 + 1);
      v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
      *a3 = v16;
      if ( v16 )
      {
        *v16 = 0;
        StringCchCopyW(*a3, (unsigned int)v15, Src);
      }
      else
      {
        v9 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            120,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)Src,
            14);
        if ( wcsistr(Src, L"xwizards.dll") )
          HrUnregisterCOMServer(a1);
        else
          HrRegisterOrUnregisterWithCOM(Src, 0);
      }
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      121,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (_DWORD)a1,
      (__int64)lpSrc,
      FullNonHardCodedPath);
  return v9;
}

```

## disassembly

```asm
0x18000daac  push    rbp
0x18000daae  push    rbx
0x18000daaf  push    rsi
0x18000dab0  push    rdi
0x18000dab1  push    r12
0x18000dab3  push    r13
0x18000dab5  push    r14
0x18000dab7  push    r15
0x18000dab9  lea     rbp, [rsp-168h]
0x18000dac1  sub     rsp, 268h
0x18000dac8  mov     rax, cs:__security_cookie
0x18000dacf  xor     rax, rsp
0x18000dad2  mov     [rbp+1A0h+var_50], rax
0x18000dad9  xor     r12d, r12d
0x18000dadc  mov     r15, r9
0x18000dadf  mov     [rsp+2A0h+pv], r12
0x18000dae4  mov     rdi, r8
0x18000dae7  mov     r14, rdx
0x18000daea  mov     rsi, rcx
0x18000daed  test    r8, r8
0x18000daf0  jz      short loc_18000DAF5
0x18000daf2  mov     [r8], r12
0x18000daf5  lea     rdx, [rsp+2A0h+pv]; unsigned __int16 **
0x18000dafa  call    ?HrVerifyCOMRegistration@@YAJQEAGQEAPEAG@Z; HrVerifyCOMRegistration(ushort * const,ushort * * const)
0x18000daff  lea     r13, WPP_GLOBAL_Control
0x18000db06  mov     ebx, eax
0x18000db08  test    eax, eax
0x18000db0a  jnz     short loc_18000DB4D
0x18000db0c  mov     rbx, [rsp+2A0h+pv]
0x18000db11  lea     rdx, aXwizardsDll; "xwizards.dll"
0x18000db18  mov     rcx, rbx; unsigned __int16 *
0x18000db1b  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000db20  test    rax, rax
0x18000db23  jz      short loc_18000DB30
0x18000db25  mov     rdx, r15; void *
0x18000db28  mov     rcx, rsi; unsigned __int16 *
0x18000db2b  call    ?HrWriteManifestCOMEntry@@YAJQEAGQEAX@Z; HrWriteManifestCOMEntry(ushort * const,void * const)
0x18000db30  test    rdi, rdi
0x18000db33  jz      short loc_18000DB3A
0x18000db35  mov     [rdi], rbx
0x18000db38  jmp     short loc_18000DB43
0x18000db3a  mov     rcx, rbx; pv
0x18000db3d  call    cs:__imp_CoTaskMemFree
0x18000db43  mov     ebx, 1
0x18000db48  jmp     loc_18000DCE6
0x18000db4d  cmp     eax, 1
0x18000db50  jnz     loc_18000DCE6
0x18000db56  test    r14, r14
0x18000db59  jz      loc_18000DCAF
0x18000db5f  lea     rdx, [rsp+2A0h+Src]; unsigned __int16 *
0x18000db64  mov     rcx, r14; lpSrc
0x18000db67  call    ?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z; HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)
0x18000db6c  mov     ebx, eax
0x18000db6e  test    eax, eax
0x18000db70  js      loc_18000DC72
0x18000db76  lea     rdx, aXwizardsDll; "xwizards.dll"
0x18000db7d  lea     rcx, [rsp+2A0h+Src]; unsigned __int16 *
0x18000db82  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000db87  lea     rcx, [rsp+2A0h+Src]; lpSrc
0x18000db8c  test    rax, rax
0x18000db8f  jz      short loc_18000DBA8
0x18000db91  mov     rdx, rsi; unsigned __int16 *
0x18000db94  call    ?HrRegisterCOMServer@@YAJPEBG0000@Z; HrRegisterCOMServer(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000db99  mov     rdx, r15; void *
0x18000db9c  mov     rcx, rsi; unsigned __int16 *
0x18000db9f  mov     ebx, eax
0x18000dba1  call    ?HrWriteManifestCOMEntry@@YAJQEAGQEAX@Z; HrWriteManifestCOMEntry(ushort * const,void * const)
0x18000dba6  jmp     short loc_18000DBB4
0x18000dba8  mov     edx, 1; int
0x18000dbad  call    ?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z; HrRegisterOrUnregisterWithCOM(ushort * const,int)
0x18000dbb2  mov     ebx, eax
0x18000dbb4  test    ebx, ebx
0x18000dbb6  js      loc_18000DCE6
0x18000dbbc  test    rdi, rdi
0x18000dbbf  jz      loc_18000DCE6
0x18000dbc5  lea     rcx, [rsp+2A0h+Src]
0x18000dbca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dbce  inc     rax
0x18000dbd1  cmp     [rcx+rax*2], r12w
0x18000dbd6  jnz     short loc_18000DBCE
0x18000dbd8  inc     eax
0x18000dbda  mov     r14d, eax
0x18000dbdd  lea     rcx, [rax+rax]; cb
0x18000dbe1  call    cs:__imp_CoTaskMemAlloc
0x18000dbe7  mov     [rdi], rax
0x18000dbea  test    rax, rax
0x18000dbed  jz      short loc_18000DC08
0x18000dbef  mov     [rax], r12w
0x18000dbf3  lea     r8, [rsp+2A0h+Src]; unsigned __int16 *
0x18000dbf8  mov     rcx, [rdi]; unsigned __int16 *
0x18000dbfb  mov     edx, r14d; unsigned __int64
0x18000dbfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dc03  jmp     loc_18000DCE6
0x18000dc08  mov     ebx, 8007000Eh
0x18000dc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc14  cmp     rcx, r13
0x18000dc17  jz      short loc_18000DC41
0x18000dc19  test    byte ptr [rcx+1Ch], 4
0x18000dc1d  jz      short loc_18000DC41
0x18000dc1f  mov     rcx, [rcx+10h]
0x18000dc23  lea     r9, [rsp+2A0h+Src]
0x18000dc28  mov     edx, 78h ; 'x'
0x18000dc2d  mov     dword ptr [rsp+2A0h+var_280], 8007000Eh
0x18000dc35  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dc3c  call    WPP_SF_SD
0x18000dc41  lea     rdx, aXwizardsDll; "xwizards.dll"
0x18000dc48  lea     rcx, [rsp+2A0h+Src]; unsigned __int16 *
0x18000dc4d  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000dc52  test    rax, rax
0x18000dc55  jz      short loc_18000DC64
0x18000dc57  mov     rcx, rsi; unsigned __int16 *
0x18000dc5a  call    ?HrUnregisterCOMServer@@YAJPEBG@Z; HrUnregisterCOMServer(ushort const *)
0x18000dc5f  jmp     loc_18000DCE6
0x18000dc64  xor     edx, edx; int
0x18000dc66  lea     rcx, [rsp+2A0h+Src]; lpSrc
0x18000dc6b  call    ?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z; HrRegisterOrUnregisterWithCOM(ushort * const,int)
0x18000dc70  jmp     short loc_18000DCE6
0x18000dc72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc79  cmp     rcx, r13
0x18000dc7c  jz      loc_18000DD10
0x18000dc82  test    byte ptr [rcx+1Ch], 4
0x18000dc86  jz      loc_18000DD10
0x18000dc8c  mov     rcx, [rcx+10h]
0x18000dc90  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dc97  mov     edx, 79h ; 'y'
0x18000dc9c  mov     [rsp+2A0h+var_278], ebx
0x18000dca0  mov     r9, rsi
0x18000dca3  mov     [rsp+2A0h+var_280], r14
0x18000dca8  call    WPP_SF_SSD
0x18000dcad  jmp     short loc_18000DD10
0x18000dcaf  mov     ebx, 80040154h
0x18000dcb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcbb  cmp     rcx, r13
0x18000dcbe  jz      short loc_18000DD10
0x18000dcc0  test    byte ptr [rcx+1Ch], 4
0x18000dcc4  jz      short loc_18000DCE6
0x18000dcc6  mov     rcx, [rcx+10h]
0x18000dcca  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dcd1  mov     edx, 7Ah ; 'z'
0x18000dcd6  mov     dword ptr [rsp+2A0h+var_280], 80040154h
0x18000dcde  mov     r9, rsi
0x18000dce1  call    WPP_SF_SD
0x18000dce6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dced  cmp     rcx, r13
0x18000dcf0  jz      short loc_18000DD10
0x18000dcf2  test    byte ptr [rcx+1Ch], 10h
0x18000dcf6  jz      short loc_18000DD10
0x18000dcf8  mov     rcx, [rcx+10h]
0x18000dcfc  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dd03  mov     edx, 7Bh ; '{'
0x18000dd08  mov     r9d, ebx
0x18000dd0b  call    WPP_SF_D
0x18000dd10  mov     eax, ebx
0x18000dd12  mov     rcx, [rbp+1A0h+var_50]
0x18000dd19  xor     rcx, rsp; StackCookie
0x18000dd1c  call    __security_check_cookie
0x18000dd21  add     rsp, 268h
0x18000dd28  pop     r15
0x18000dd2a  pop     r14
0x18000dd2c  pop     r13
0x18000dd2e  pop     r12
0x18000dd30  pop     rdi
0x18000dd31  pop     rsi
0x18000dd32  pop     rbx
0x18000dd33  pop     rbp
0x18000dd34  retn
```
