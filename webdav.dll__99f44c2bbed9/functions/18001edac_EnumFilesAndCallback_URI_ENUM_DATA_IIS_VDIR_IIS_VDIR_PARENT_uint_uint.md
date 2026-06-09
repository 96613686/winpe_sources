# EnumFilesAndCallback(URI_ENUM_DATA *,IIS_VDIR *,IIS_VDIR_PARENT *,uint,uint)

- ea: `0x18001edac`
- end: `0x18001ef9e`
- name: `?EnumFilesAndCallback@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@PEAVIIS_VDIR_PARENT@@II@Z`
- size: `498`
- prototype: `__int64 __usercall@<rax>(struct URI_ENUM_DATA *@<rcx>, struct IIS_VDIR *@<rdx>, struct IIS_VDIR_PARENT *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f35c`

## callees

- `0x1800043b0`
- `0x18001edac`
- `0x18001faf0`
- `0x18001fc18`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001ee73`
- `msvcrt!_wcsicmp` at `0x18001ee73`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ef22`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ef22`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ef86`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ef86`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001ef63`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001ef6d`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001ef63`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001ef6d`

## pseudocode

```c
__int64 __fastcall EnumFilesAndCallback(
        struct URI_ENUM_DATA *a1,
        struct IIS_VDIR *a2,
        struct IIS_VDIR_PARENT *a3,
        unsigned int a4,
        unsigned int a5)
{
  int started; // r13d
  int v7; // r12d
  _DWORD *v8; // rdi
  int v9; // r14d
  int v10; // r8d
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  HANDLE hFindFile; // [rsp+80h] [rbp+8h] BYREF
  struct IIS_VDIR *v14; // [rsp+88h] [rbp+10h]
  struct IIS_VDIR_PARENT *v15; // [rsp+90h] [rbp+18h]
  unsigned int v16; // [rsp+98h] [rbp+20h]

  v16 = a4;
  v15 = a3;
  v14 = a2;
  hFindFile = (HANDLE)-1LL;
  started = StartUriEnum(a1, a2, a4, a5, &hFindFile);
  if ( started < 0 )
    goto LABEL_22;
  v7 = 1;
  if ( hFindFile == (HANDLE)-1LL )
    goto LABEL_22;
  while ( 1 )
  {
    v8 = (_DWORD *)((char *)a1 + 164);
    if ( *((_WORD *)a1 + 104) != 46 )
      break;
    if ( *((_WORD *)a1 + 105) && (*((_WORD *)a1 + 105) != 46 || *((_WORD *)a1 + 106)) )
    {
      v8 = (_DWORD *)((char *)a1 + 164);
      break;
    }
LABEL_18:
    if ( !FindNextFileW(hFindFile, (LPWIN32_FIND_DATAW)((char *)a1 + 164)) )
      goto LABEL_21;
  }
  v9 = *((_DWORD *)a1 + 36);
  if ( (v9 & 8) == 0 && (*(_BYTE *)v8 & 2) != 0 )
    goto LABEL_18;
  if ( (v9 & 0x10) == 0 && (*(_BYTE *)v8 & 4) != 0 )
    goto LABEL_18;
  if ( !_wcsicmp((const wchar_t *)a1 + 104, L"properties.dav") && (v9 & 2) == 0 )
    goto LABEL_18;
  if ( v15 )
  {
    Key = STATIC_WSTRING_HASH::FindKey(
            (struct IIS_VDIR_PARENT *)((char *)v15 + 24),
            (const unsigned __int16 *)a1 + 104,
            v10);
    if ( (-(__int64)(Key != 0) & ((unsigned __int64)Key - 24)) != 0 )
      goto LABEL_18;
  }
  started = UpdateUriEnumData(a1, v16, a5, (const unsigned __int16 *)a1 + 104, (*v8 >> 4) & 1);
  if ( started >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct IIS_VDIR *, _QWORD, _QWORD, _DWORD, _DWORD))(**((_QWORD **)a1 + 2)
                                                                                              + 8LL))(
           *((_QWORD *)a1 + 2),
           v14,
           *((_QWORD *)a1 + 8),
           *((_QWORD *)a1 + 15),
           *((_DWORD *)a1 + 37),
           *v8);
    if ( !v7 )
      goto LABEL_21;
    goto LABEL_18;
  }
  v7 = 0;
LABEL_21:
  *((_DWORD *)a1 + 38) = v7;
LABEL_22:
  *(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * v16) = 0;
  *(_WORD *)(*((_QWORD *)a1 + 15) + 2LL * a5) = 0;
  STRU::SyncWithBuffer((struct URI_ENUM_DATA *)((char *)a1 + 32));
  STRU::SyncWithBuffer((struct URI_ENUM_DATA *)((char *)a1 + 88));
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001edac  mov     rax, rsp
0x18001edaf  mov     [rax+20h], r9d
0x18001edb3  mov     [rax+18h], r8
0x18001edb7  mov     [rax+10h], rdx
0x18001edbb  push    rbx
0x18001edbc  push    rbp
0x18001edbd  push    rsi
0x18001edbe  push    rdi
0x18001edbf  push    r12
0x18001edc1  push    r13
0x18001edc3  push    r14
0x18001edc5  sub     rsp, 40h
0x18001edc9  mov     rbx, rcx
0x18001edcc  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18001edd4  lea     rcx, [rax+8]
0x18001edd8  mov     r8d, r9d; unsigned int
0x18001eddb  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x18001ede3  mov     [rax-58h], rcx
0x18001ede7  mov     rcx, rbx; struct URI_ENUM_DATA *
0x18001edea  call    ?StartUriEnum@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@IIPEAPEAX@Z; StartUriEnum(URI_ENUM_DATA *,IIS_VDIR *,uint,uint,void * *)
0x18001edef  xor     ecx, ecx
0x18001edf1  mov     r13d, eax
0x18001edf4  test    eax, eax
0x18001edf6  js      loc_18001EF3D
0x18001edfc  cmp     [rsp+78h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001ee05  lea     r12d, [rcx+1]
0x18001ee09  jz      loc_18001EF3D
0x18001ee0f  lea     rsi, [rbx+0D0h]
0x18001ee16  lea     rbp, [rbx+0A4h]
0x18001ee1d  cmp     word ptr [rsi], 2Eh ; '.'
0x18001ee21  mov     rdi, rbp
0x18001ee24  jnz     short loc_18001EE44
0x18001ee26  cmp     [rsi+2], cx
0x18001ee2a  jz      loc_18001EF17
0x18001ee30  cmp     word ptr [rsi+2], 2Eh ; '.'
0x18001ee35  jnz     short loc_18001EE41
0x18001ee37  cmp     [rsi+4], cx
0x18001ee3b  jz      loc_18001EF17
0x18001ee41  mov     rdi, rbp
0x18001ee44  mov     r14d, [rbx+90h]
0x18001ee4b  test    r14b, 8
0x18001ee4f  jnz     short loc_18001EE5A
0x18001ee51  test    byte ptr [rdi], 2
0x18001ee54  jnz     loc_18001EF17
0x18001ee5a  test    r14b, 10h
0x18001ee5e  jnz     short loc_18001EE69
0x18001ee60  test    byte ptr [rdi], 4
0x18001ee63  jnz     loc_18001EF17
0x18001ee69  lea     rdx, aPropertiesDav; "properties.dav"
0x18001ee70  mov     rcx, rsi; String1
0x18001ee73  call    cs:__imp__wcsicmp
0x18001ee79  test    eax, eax
0x18001ee7b  jnz     short loc_18001EE87
0x18001ee7d  test    r14b, 2
0x18001ee81  jz      loc_18001EF17
0x18001ee87  mov     r14, [rsp+78h+arg_10]
0x18001ee8f  test    r14, r14
0x18001ee92  jz      short loc_18001EEAF
0x18001ee94  lea     rcx, [r14+18h]; this
0x18001ee98  mov     rdx, rsi; unsigned __int16 *
0x18001ee9b  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18001eea0  lea     rcx, [rax-18h]
0x18001eea4  neg     rax
0x18001eea7  sbb     rax, rax
0x18001eeaa  test    rcx, rax
0x18001eead  jnz     short loc_18001EF17
0x18001eeaf  mov     eax, [rdi]
0x18001eeb1  mov     r9, rsi; unsigned __int16 *
0x18001eeb4  mov     r8d, [rsp+78h+arg_20]; unsigned int
0x18001eebc  mov     rcx, rbx; struct URI_ENUM_DATA *
0x18001eebf  mov     edx, [rsp+78h+arg_18]; unsigned int
0x18001eec6  shr     eax, 4
0x18001eec9  and     eax, 1
0x18001eecc  mov     [rsp+78h+var_58], eax; int
0x18001eed0  call    ?UpdateUriEnumData@@YAJPEAVURI_ENUM_DATA@@IIPEBGH@Z; UpdateUriEnumData(URI_ENUM_DATA *,uint,uint,ushort const *,int)
0x18001eed5  xor     ecx, ecx
0x18001eed7  mov     r13d, eax
0x18001eeda  test    eax, eax
0x18001eedc  js      short loc_18001EF33
0x18001eede  mov     edx, [rdi]
0x18001eee0  mov     rcx, [rbx+10h]
0x18001eee4  mov     r9, [rbx+78h]
0x18001eee8  mov     r8, [rbx+40h]
0x18001eeec  mov     [rsp+78h+var_50], edx
0x18001eef0  mov     edx, [rbx+94h]
0x18001eef6  mov     rax, [rcx]
0x18001eef9  mov     [rsp+78h+var_58], edx
0x18001eefd  mov     rdx, [rsp+78h+arg_8]
0x18001ef05  mov     rax, [rax+8]
0x18001ef09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef0e  xor     ecx, ecx
0x18001ef10  mov     r12d, eax
0x18001ef13  test    eax, eax
0x18001ef15  jz      short loc_18001EF36
0x18001ef17  mov     rcx, [rsp+78h+hFindFile]; hFindFile
0x18001ef1f  mov     rdx, rbp; lpFindFileData
0x18001ef22  call    cs:__imp_FindNextFileW
0x18001ef28  xor     ecx, ecx
0x18001ef2a  test    eax, eax
0x18001ef2c  jz      short loc_18001EF36
0x18001ef2e  jmp     loc_18001EE1D
0x18001ef33  mov     r12d, ecx
0x18001ef36  mov     [rbx+98h], r12d
0x18001ef3d  mov     rdx, [rbx+40h]
0x18001ef41  mov     r8d, [rsp+78h+arg_18]
0x18001ef49  mov     [rdx+r8*2], cx
0x18001ef4e  mov     r8d, [rsp+78h+arg_20]
0x18001ef56  mov     rdx, [rbx+78h]
0x18001ef5a  mov     [rdx+r8*2], cx
0x18001ef5f  lea     rcx, [rbx+20h]
0x18001ef63  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001ef69  lea     rcx, [rbx+58h]
0x18001ef6d  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001ef73  cmp     [rsp+78h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001ef7c  jz      short loc_18001EF8C
0x18001ef7e  mov     rcx, [rsp+78h+hFindFile]; hFindFile
0x18001ef86  call    cs:__imp_FindClose
0x18001ef8c  mov     eax, r13d
0x18001ef8f  add     rsp, 40h
0x18001ef93  pop     r14
0x18001ef95  pop     r13
0x18001ef97  pop     r12
0x18001ef99  pop     rdi
0x18001ef9a  pop     rsi
0x18001ef9b  pop     rbp
0x18001ef9c  pop     rbx
0x18001ef9d  retn
```
