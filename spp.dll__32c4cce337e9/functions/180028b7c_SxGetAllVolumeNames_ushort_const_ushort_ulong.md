# SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)

- ea: `0x180028b7c`
- end: `0x180028ee0`
- name: `?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011fb0`

## callees

- `0x18000702c`
- `0x18000e040`
- `0x180020908`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002758c`
- `0x180027638`
- `0x18002849c`
- `0x180028b7c`
- `0x18002be5c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028d12`
- `KERNEL32!GetLastError` at `0x180028d12`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180028d04`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180028d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028eaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028eaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028cd7`

## pseudocode

```c
__int64 __fastcall SxGetAllVolumeNames(const unsigned __int16 *a1, unsigned __int16 ***a2, unsigned int *a3)
{
  void *v6; // r12
  void *v7; // rdi
  unsigned __int16 *v8; // rsi
  __int16 v9; // ax
  int AllVolumeGUIDNames; // eax
  bool v11; // sf
  const WCHAR *v12; // rbx
  DWORD v13; // eax
  signed int LastError; // eax
  const unsigned __int16 *i; // rbx
  int v16; // eax
  __int64 v17; // rax
  void *v18; // rcx
  unsigned __int16 **v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int j; // esi
  __int64 v23; // rbx
  LPVOID *v24; // rcx
  unsigned int k; // esi
  __int64 v26; // rbx
  unsigned int v27; // ebx
  unsigned __int16 *v29; // [rsp+30h] [rbp-48h] BYREF
  int v30; // [rsp+38h] [rbp-40h] BYREF
  __int16 v31; // [rsp+3Ch] [rbp-3Ch]
  __int16 v32; // [rsp+3Eh] [rbp-3Ah]
  DWORD cchReturnLength; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v34; // [rsp+C8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+58h] BYREF
  void *Block; // [rsp+D8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v30, "SxGetAllVolumeNames", 401, 1);
  cchReturnLength = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  pv = 0;
  v34 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 418;
  if ( !a1 || (v31 = 418, v9 = 419, !a2) || (v31 = 419, v9 = 420, !a3) )
  {
    v30 = -2147024809;
    goto LABEL_38;
  }
  v30 = 0;
  v31 = 420;
  v30 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v9 = 422;
  if ( v30 < 0 )
  {
    v7 = Block;
LABEL_38:
    v32 = v9;
    goto LABEL_39;
  }
  v31 = 422;
  AllVolumeGUIDNames = SxGetAllVolumeGUIDNames(a1, (unsigned __int16 ***)&pv, &v34);
  v7 = Block;
  v11 = AllVolumeGUIDNames < 0;
  v30 = AllVolumeGUIDNames;
  v9 = 427;
  if ( v11 )
    goto LABEL_38;
  v31 = 427;
  v30 = CSxSimpleArray<unsigned short *>::Attach(Block, v34, &pv);
  v9 = 428;
  if ( v30 < 0 )
    goto LABEL_38;
  v31 = 428;
  v12 = (const WCHAR *)**((_QWORD **)v7 + 1);
  v13 = 261;
  for ( cchReturnLength = 261; ; v13 = cchReturnLength )
  {
    v6 = CoTaskMemRealloc(v6, 2LL * v13);
    v9 = 443;
    if ( !v6 )
    {
      v30 = -2147024882;
      goto LABEL_38;
    }
    v30 = 0;
    v31 = 443;
    if ( GetVolumePathNamesForVolumeNameW(v12, (LPWCH)v6, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v30 = LastError;
    if ( LastError < 0 )
    {
      v32 = 453;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)v12,
          LastError);
      goto LABEL_39;
    }
    v31 = 453;
  }
  for ( i = (const unsigned __int16 *)v6; *i; i += v17 + 1 )
  {
    v16 = SxCopyString(i, &v29);
    v8 = v29;
    v11 = v16 < 0;
    v30 = v16;
    v9 = 463;
    if ( v11 )
      goto LABEL_38;
    v31 = 463;
    v30 = CSxSimpleArray<unsigned short *>::Append((__int64)v7, (__int64)v29);
    v9 = 464;
    if ( v30 < 0 )
      goto LABEL_38;
    v31 = 464;
    v8 = 0;
    v17 = -1;
    v29 = 0;
    do
      ++v17;
    while ( i[v17] );
  }
  v18 = v7;
  *a3 = *((_DWORD *)v7 + 4);
  v19 = (unsigned __int16 **)*((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v7 = 0;
  *a2 = v19;
  CSxSimpleArray<_GUID>::Release(v18);
LABEL_39:
  CoTaskMemFree(v6);
  CoTaskMemFree(v8);
  if ( v7 )
  {
    for ( j = 0; j < *((_DWORD *)v7 + 4); *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v23) = 0 )
    {
      v23 = j;
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 1) + 8LL * j++));
    }
  }
  v24 = (LPVOID *)pv;
  if ( pv )
  {
    for ( k = 0; k < v34; v24 = (LPVOID *)pv )
    {
      v26 = k;
      CoTaskMemFree(v24[k++]);
      *((_QWORD *)pv + v26) = 0;
    }
    CoTaskMemFree(v24);
    pv = 0;
  }
  v27 = v30;
  if ( v7 )
    CSxSimpleArray<_GUID>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v30, v20, v21);
  return v27;
}

```

## disassembly

```asm
0x180028b7c  push    rbp
0x180028b7e  push    rbx
0x180028b7f  push    rsi
0x180028b80  push    rdi
0x180028b81  push    r12
0x180028b83  push    r13
0x180028b85  push    r14
0x180028b87  push    r15
0x180028b89  mov     rbp, rsp
0x180028b8c  sub     rsp, 78h
0x180028b90  mov     r14, r8
0x180028b93  mov     r15, rdx
0x180028b96  mov     rbx, rcx
0x180028b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ba0  lea     rax, WPP_GLOBAL_Control
0x180028ba7  cmp     rcx, rax
0x180028baa  jz      short loc_180028BCD
0x180028bac  test    dword ptr [rcx+1Ch], 20000000h
0x180028bb3  jz      short loc_180028BCD
0x180028bb5  mov     rcx, [rcx+10h]
0x180028bb9  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180028bc0  mov     edx, 10h
0x180028bc5  mov     r9, rbx
0x180028bc8  call    WPP_SF_S
0x180028bcd  mov     r9d, 1; unsigned __int16
0x180028bd3  lea     rdx, aSxgetallvolume_0; "SxGetAllVolumeNames"
0x180028bda  mov     r8d, 191h; unsigned __int16
0x180028be0  lea     rcx, [rbp+var_40]; this
0x180028be4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180028be9  xor     r13d, r13d
0x180028bec  mov     [rbp+cchReturnLength], r13d
0x180028bf0  mov     r12d, r13d
0x180028bf3  mov     [rbp+Block], r13
0x180028bf7  mov     edi, r13d
0x180028bfa  mov     [rbp+var_48], r13
0x180028bfe  mov     esi, r13d
0x180028c01  mov     [rbp+pv], r13
0x180028c05  mov     [rbp+arg_8], r13d
0x180028c09  test    r15, r15
0x180028c0c  jz      short loc_180028C11
0x180028c0e  mov     [r15], r13
0x180028c11  test    r14, r14
0x180028c14  jz      short loc_180028C19
0x180028c16  mov     [r14], r13d
0x180028c19  mov     eax, 1A2h
0x180028c1e  test    rbx, rbx
0x180028c21  jz      loc_180028E2F
0x180028c27  mov     [rbp+var_3C], ax
0x180028c2b  mov     eax, 1A3h
0x180028c30  test    r15, r15
0x180028c33  jz      loc_180028E2F
0x180028c39  mov     [rbp+var_3C], ax
0x180028c3d  mov     eax, 1A4h
0x180028c42  test    r14, r14
0x180028c45  jz      loc_180028E2F
0x180028c4b  lea     rcx, [rbp+Block]
0x180028c4f  mov     [rbp+var_40], r13d
0x180028c53  mov     [rbp+var_3C], ax
0x180028c57  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x180028c5c  mov     [rbp+var_40], eax
0x180028c5f  test    eax, eax
0x180028c61  mov     eax, 1A6h
0x180028c66  jns     short loc_180028C71
0x180028c68  mov     rdi, [rbp+Block]
0x180028c6c  jmp     loc_180028E36
0x180028c71  lea     r8, [rbp+arg_8]; unsigned int *
0x180028c75  mov     [rbp+var_3C], ax
0x180028c79  lea     rdx, [rbp+pv]; unsigned __int16 ***
0x180028c7d  mov     rcx, rbx; unsigned __int16 *
0x180028c80  call    ?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)
0x180028c85  mov     rdi, [rbp+Block]
0x180028c89  test    eax, eax
0x180028c8b  mov     [rbp+var_40], eax
0x180028c8e  mov     eax, 1ABh
0x180028c93  js      loc_180028E36
0x180028c99  mov     edx, [rbp+arg_8]
0x180028c9c  lea     r8, [rbp+pv]
0x180028ca0  mov     rcx, rdi
0x180028ca3  mov     [rbp+var_3C], ax
0x180028ca7  call    ?Attach@?$CSxSimpleArray@PEAG@@QEAAJKPEAPEAPEAG@Z; CSxSimpleArray<ushort *>::Attach(ulong,ushort * * *)
0x180028cac  mov     [rbp+var_40], eax
0x180028caf  test    eax, eax
0x180028cb1  mov     eax, 1ACh
0x180028cb6  js      loc_180028E36
0x180028cbc  mov     [rbp+var_3C], ax
0x180028cc0  mov     rax, [rdi+8]
0x180028cc4  mov     rbx, [rax]
0x180028cc7  mov     eax, 105h
0x180028ccc  mov     [rbp+cchReturnLength], eax
0x180028ccf  mov     edx, eax
0x180028cd1  mov     rcx, r12; pv
0x180028cd4  add     rdx, rdx; cb
0x180028cd7  call    cs:__imp_CoTaskMemRealloc
0x180028cdd  mov     r12, rax
0x180028ce0  test    rax, rax
0x180028ce3  mov     eax, 1BBh
0x180028ce8  jz      loc_180028E26
0x180028cee  mov     r8d, [rbp+cchReturnLength]; cchBufferLength
0x180028cf2  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180028cf6  mov     rdx, r12; lpszVolumePathNames
0x180028cf9  mov     [rbp+var_40], r13d
0x180028cfd  mov     rcx, rbx; lpszVolumeName
0x180028d00  mov     [rbp+var_3C], ax
0x180028d04  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180028d0a  test    eax, eax
0x180028d0c  jnz     loc_180028DA1
0x180028d12  call    cs:__imp_GetLastError
0x180028d18  cmp     eax, 7Ah ; 'z'
0x180028d1b  jz      short loc_180028D32
0x180028d1d  cmp     eax, 0EAh
0x180028d22  jz      short loc_180028D32
0x180028d24  test    eax, eax
0x180028d26  jle     short loc_180028D35
0x180028d28  movzx   eax, ax
0x180028d2b  or      eax, 80070000h
0x180028d30  jmp     short loc_180028D35
0x180028d32  mov     eax, r13d
0x180028d35  mov     [rbp+var_40], eax
0x180028d38  test    eax, eax
0x180028d3a  js      short loc_180028D4A
0x180028d3c  mov     eax, 1C5h
0x180028d41  mov     [rbp+var_3C], ax
0x180028d45  mov     eax, [rbp+cchReturnLength]
0x180028d48  jmp     short loc_180028CCF
0x180028d4a  mov     ecx, 1C5h
0x180028d4f  mov     [rbp+var_3A], cx
0x180028d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d5a  lea     rdx, WPP_GLOBAL_Control
0x180028d61  cmp     rcx, rdx
0x180028d64  jz      loc_180028E3A
0x180028d6a  test    dword ptr [rcx+1Ch], 2000000h
0x180028d71  jz      loc_180028E3A
0x180028d77  mov     rcx, [rcx+10h]
0x180028d7b  lea     r9, aDwerr; "dwErr"
0x180028d82  mov     [rsp+78h+var_50], eax
0x180028d86  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180028d8d  mov     edx, 11h
0x180028d92  mov     [rsp+78h+var_58], rbx
0x180028d97  call    WPP_SF_sSd
0x180028d9c  jmp     loc_180028E3A
0x180028da1  mov     rbx, r12
0x180028da4  cmp     [rbx], r13w
0x180028da8  jz      short loc_180028E04
0x180028daa  lea     rdx, [rbp+var_48]; unsigned __int16 **
0x180028dae  mov     rcx, rbx; Src
0x180028db1  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180028db6  mov     rsi, [rbp+var_48]
0x180028dba  test    eax, eax
0x180028dbc  mov     [rbp+var_40], eax
0x180028dbf  mov     eax, 1CFh
0x180028dc4  js      short loc_180028E36
0x180028dc6  mov     rdx, rsi
0x180028dc9  mov     [rbp+var_3C], ax
0x180028dcd  mov     rcx, rdi
0x180028dd0  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x180028dd5  mov     [rbp+var_40], eax
0x180028dd8  test    eax, eax
0x180028dda  mov     eax, 1D0h
0x180028ddf  js      short loc_180028E36
0x180028de1  mov     [rbp+var_3C], ax
0x180028de5  mov     rsi, r13
0x180028de8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028dec  mov     [rbp+var_48], r13
0x180028df0  inc     rax
0x180028df3  cmp     [rbx+rax*2], r13w
0x180028df8  jnz     short loc_180028DF0
0x180028dfa  lea     rbx, [rbx+rax*2]
0x180028dfe  add     rbx, 2
0x180028e02  jmp     short loc_180028DA4
0x180028e04  mov     eax, [rdi+10h]
0x180028e07  mov     rcx, rdi; Block
0x180028e0a  mov     [r14], eax
0x180028e0d  mov     rax, [rdi+8]
0x180028e11  mov     [rdi+8], r13
0x180028e15  mov     [rdi+10h], r13
0x180028e19  mov     rdi, r13
0x180028e1c  mov     [r15], rax
0x180028e1f  call    ?Release@?$CSxSimpleArray@U_GUID@@@@QEAAKXZ; CSxSimpleArray<_GUID>::Release(void)
0x180028e24  jmp     short loc_180028E3A
0x180028e26  mov     [rbp+var_40], 8007000Eh
0x180028e2d  jmp     short loc_180028E36
0x180028e2f  mov     [rbp+var_40], 80070057h
0x180028e36  mov     [rbp+var_3A], ax
0x180028e3a  mov     rcx, r12; pv
0x180028e3d  call    cs:__imp_CoTaskMemFree
0x180028e43  mov     rcx, rsi; pv
0x180028e46  call    cs:__imp_CoTaskMemFree
0x180028e4c  test    rdi, rdi
0x180028e4f  jz      short loc_180028E79
0x180028e51  mov     esi, r13d
0x180028e54  cmp     [rdi+10h], r13d
0x180028e58  jbe     short loc_180028E79
0x180028e5a  mov     rcx, [rdi+8]
0x180028e5e  mov     ebx, esi
0x180028e60  mov     rcx, [rcx+rbx*8]; pv
0x180028e64  call    cs:__imp_CoTaskMemFree
0x180028e6a  mov     rax, [rdi+8]
0x180028e6e  inc     esi
0x180028e70  mov     [rax+rbx*8], r13
0x180028e74  cmp     esi, [rdi+10h]
0x180028e77  jb      short loc_180028E5A
0x180028e79  mov     rcx, [rbp+pv]
0x180028e7d  test    rcx, rcx
0x180028e80  jz      short loc_180028EB4
0x180028e82  mov     esi, r13d
0x180028e85  cmp     [rbp+arg_8], r13d
0x180028e89  jbe     short loc_180028EAA
0x180028e8b  mov     ebx, esi
0x180028e8d  mov     rcx, [rcx+rbx*8]; pv
0x180028e91  call    cs:__imp_CoTaskMemFree
0x180028e97  mov     rax, [rbp+pv]
0x180028e9b  inc     esi
0x180028e9d  mov     [rax+rbx*8], r13
0x180028ea1  mov     rcx, [rbp+pv]; pv
0x180028ea5  cmp     esi, [rbp+arg_8]
0x180028ea8  jb      short loc_180028E8B
0x180028eaa  call    cs:__imp_CoTaskMemFree
0x180028eb0  mov     [rbp+pv], r13
0x180028eb4  mov     ebx, [rbp+var_40]
0x180028eb7  test    rdi, rdi
0x180028eba  jz      short loc_180028EC4
0x180028ebc  mov     rcx, rdi; Block
0x180028ebf  call    ?Release@?$CSxSimpleArray@U_GUID@@@@QEAAKXZ; CSxSimpleArray<_GUID>::Release(void)
0x180028ec4  lea     rcx, [rbp+var_40]; this
0x180028ec8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180028ecd  mov     eax, ebx
0x180028ecf  add     rsp, 78h
0x180028ed3  pop     r15
0x180028ed5  pop     r14
0x180028ed7  pop     r13
0x180028ed9  pop     r12
0x180028edb  pop     rdi
0x180028edc  pop     rsi
0x180028edd  pop     rbx
0x180028ede  pop     rbp
0x180028edf  retn
```
