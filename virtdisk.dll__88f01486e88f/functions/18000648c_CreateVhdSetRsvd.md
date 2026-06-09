# CreateVhdSetRsvd

- ea: `0x18000648c`
- end: `0x180006aa3`
- name: `CreateVhdSetRsvd`
- size: `1559`
- prototype: `__int64 __fastcall(wchar_t *Str, __int64, VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask, void *, int, ULONG ProviderSpecificFlags, __int64, const WCHAR *, int, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x180002740`
- `0x180005730`
- `0x180005fd6`
- `0x18000648c`
- `0x180006aac`
- `0x180006fdc`
- `0x18000707c`
- `0x18000712c`
- `0x1800071f4`
- `0x18000a27c`
- `0x18000a3f8`
- `0x18000a634`
- `0x18000a76c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a0f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a2c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a0f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000683f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000683f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006708`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000693c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006708`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000693c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000675d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000696b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000675d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18000696b`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000682f`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000682f`
- `ntdll!RtlFreeHeap` at `0x180006920`
- `ntdll!RtlFreeHeap` at `0x180006920`
- `ntdll!RtlInitUnicodeString` at `0x1800065b8`
- `ntdll!RtlInitUnicodeString` at `0x1800065b8`

## pseudocode

```c
__int64 __fastcall CreateVhdSetRsvd(
        wchar_t *Str,
        __int64 a2,
        VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask,
        void *a4,
        int a5,
        ULONG ProviderSpecificFlags,
        __int64 a7,
        const WCHAR *a8,
        int a9,
        __int64 *a10)
{
  __int64 v12; // rsi
  __int64 v14; // rdx
  __int128 v15; // xmm0
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __m128i v18; // xmm2
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  unsigned int BackingFilePath; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  const WCHAR *v30; // rdi
  unsigned int v31; // ebx
  DWORD LastError; // eax
  _QWORD *v33; // rcx
  int v34; // edx
  char v35; // r13
  __int64 *v36; // r15
  unsigned int v37; // eax
  unsigned int v38; // eax
  char v39; // al
  int v40; // esi
  char v42; // [rsp+51h] [rbp-AFh]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR Path; // [rsp+80h] [rbp-80h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  PWSTR v49; // [rsp+98h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+C0h] [rbp-40h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+180h] [rbp+80h] BYREF
  __int64 v54[2]; // [rsp+198h] [rbp+98h]

  v54[0] = a2;
  hObject = (HANDLE)-1LL;
  v12 = -1;
  hFile = (HANDLE)-1LL;
  *((_DWORD *)&Parameters.Version + 1) = 0;
  SecurityDescriptor = a4;
  v42 = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
  memset_0(&Parameters, 0, 0xB4u);
  v49 = 0;
  Path = 0;
  v46 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SZdd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (a5 & 8) != 0, (a5 & 0x40) != 0);
  }
  *a10 = -1;
  RtlInitUnicodeString(&DestinationString, Str);
  if ( *(int *)a7 < 3 )
  {
    VirtualStorageType.DeviceId = 3;
    VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  }
  else
  {
    v15 = *(_OWORD *)(a7 + 136);
    *(_DWORD *)&VirtualStorageType.VendorId.Data4[4] = *(_DWORD *)(a7 + 152);
    *(_OWORD *)&VirtualStorageType.DeviceId = v15;
  }
  v16 = *(_OWORD *)(a7 + 16);
  v17 = *(_OWORD *)(a7 + 32);
  Parameters.Version4.DataAlignment = *(_QWORD *)(a7 + 176);
  v18 = *(__m128i *)a7;
  *(_OWORD *)Parameters.Version4.UniqueId.Data4 = v16;
  v19 = *(_OWORD *)(a7 + 48);
  *(_OWORD *)&Parameters.Version4.BlockSizeInBytes = v17;
  v20 = *(_OWORD *)(a7 + 64);
  *(_OWORD *)&Parameters.Version4.ParentPath = v19;
  v21 = *(_OWORD *)(a7 + 80);
  *(_OWORD *)&Parameters.Version4.OpenFlags = v20;
  v22 = *(_OWORD *)(a7 + 96);
  *(_OWORD *)Parameters.Version4.ParentVirtualStorageType.VendorId.Data4 = v21;
  v23 = *(_OWORD *)(a7 + 112);
  *(_OWORD *)&Parameters.Version4.SourceVirtualStorageType.VendorId.Data2 = v22;
  v24 = *(_OWORD *)(a7 + 128);
  *(_OWORD *)&Parameters.Version4.ResiliencyGuid.Data2 = v23;
  v25 = *(_OWORD *)(a7 + 144);
  *(_OWORD *)&Parameters.Version4.SourceLimitPath = v24;
  v26 = *(_OWORD *)(a7 + 160);
  *(_OWORD *)&Parameters.Version4.BackingStorageType.VendorId.Data2 = v25;
  *(__m128i *)&Parameters.Version = v18;
  *(_OWORD *)&Parameters.Version4.PmemAddressAbstractionType.Data2 = v26;
  if ( _mm_cvtsi128_si32(v18) >= 2 )
    Parameters.Version2.OpenFlags &= ~0x40u;
  BackingFilePath = GetBackingFilePath(Str, v14, &v49, (_DWORD *)&v46 + 1, (PWSTR *)&Path, &v46);
  v30 = Path;
  v31 = BackingFilePath;
  if ( BackingFilePath )
    goto LABEL_43;
  if ( a8 )
  {
    if ( (a5 & 0x40) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v29, (_DWORD)a8, (__int64)Path);
      }
      if ( !MoveFileW(a8, v30) )
      {
        LastError = GetLastError();
        v31 = LastError;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_25;
        }
        v34 = 12;
LABEL_24:
        WPP_SF_SSd(v33[2], v34, v29, (_DWORD)a8, (__int64)v30, LastError);
        v33 = WPP_GLOBAL_Control;
LABEL_25:
        v35 = 0;
        goto LABEL_26;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v29, (_DWORD)a8, (__int64)Path);
      }
      if ( !CopyFileExW(a8, v30, 0, 0, 0, 0x8000u) )
      {
        LastError = GetLastError();
        v31 = LastError;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_25;
        }
        v34 = 14;
        goto LABEL_24;
      }
    }
    v42 = 1;
    goto LABEL_38;
  }
  v31 = CreateVirtualDisk(
          &VirtualStorageType,
          Path,
          VirtualDiskAccessMask,
          SecurityDescriptor,
          (CREATE_VIRTUAL_DISK_FLAG)(a5 & 0xFFFFFFBD),
          ProviderSpecificFlags,
          &Parameters,
          0,
          &hObject);
  if ( v31 )
  {
LABEL_43:
    v35 = 0;
LABEL_44:
    v33 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v42 = 1;
  CloseHandle(hObject);
LABEL_38:
  v31 = ConvertVhdxToVhdSetRsvd(v30, (const void **)v54[0]);
  if ( v31 )
    goto LABEL_43;
  v35 = 1;
  v31 = ConstructRsvdPathToFile(&DestinationString, (struct _UNICODE_STRING *)P, v29);
  if ( v31 )
    goto LABEL_44;
  v37 = OpenPathForRsvd(P, v28, &hFile);
  v12 = (__int64)hFile;
  v31 = v37;
  if ( v37 )
    goto LABEL_44;
  if ( (a5 & 8) != 0 )
    goto LABEL_27;
  *(_OWORD *)v54 = 0;
  v38 = DeleteVhdSetSnapshotRsvd(hFile);
  v33 = WPP_GLOBAL_Control;
  v31 = v38;
LABEL_26:
  if ( !v31 )
  {
LABEL_27:
    v36 = a10;
    *a10 = v12;
    v12 = -1;
    v33 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
LABEL_45:
  v36 = a10;
LABEL_46:
  if ( P[1] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    v33 = WPP_GLOBAL_Control;
  }
  if ( v12 != -1 )
  {
    CloseHandle((HANDLE)v12);
    v33 = WPP_GLOBAL_Control;
  }
  if ( !v31 )
  {
    v40 = (int)Str;
    goto LABEL_66;
  }
  if ( v35 )
  {
    if ( (a5 & 0x40) == 0 )
    {
      v40 = (int)Str;
      DeleteFileW(Str);
      v33 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    if ( MoveFileW(v30, a8) )
    {
      v33 = WPP_GLOBAL_Control;
    }
    else
    {
      v39 = GetLastError();
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v29, (_DWORD)v30, (__int64)a8, v39);
        v33 = WPP_GLOBAL_Control;
      }
    }
  }
  v40 = (int)Str;
LABEL_60:
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    v33 = WPP_GLOBAL_Control;
    hObject = (HANDLE)-1LL;
  }
  if ( v42 )
  {
    DeleteFileW(v30);
    v33 = WPP_GLOBAL_Control;
  }
LABEL_66:
  if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x20) != 0 && *((_BYTE *)v33 + 25) >= 4u )
    WPP_SF_SDq(v33[2], v28, v29, v40, v31, *v36);
  return v31;
}

```

## disassembly

```asm
0x18000648c  push    rbp
0x18000648e  push    rbx
0x18000648f  push    rsi
0x180006490  push    rdi
0x180006491  push    r12
0x180006493  push    r13
0x180006495  push    r14
0x180006497  push    r15
0x180006499  lea     rbp, [rsp-0B8h]
0x1800064a1  sub     rsp, 1B8h
0x1800064a8  mov     rax, cs:__security_cookie
0x1800064af  xor     rax, rsp
0x1800064b2  mov     [rbp+0F0h+var_48], rax
0x1800064b9  mov     rax, [rbp+0F0h+arg_48]
0x1800064c0  xor     r15d, r15d
0x1800064c3  mov     rbx, [rbp+0F0h+arg_30]
0x1800064ca  xorps   xmm0, xmm0
0x1800064cd  mov     r14, [rbp+0F0h+arg_38]
0x1800064d4  mov     r13d, r8d
0x1800064d7  mov     [rsp+1F0h+var_190], rax
0x1800064dc  mov     r12, rdx
0x1800064df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800064e3  mov     [rbp+0F0h+var_58], rdx
0x1800064ea  mov     [rsp+1F0h+hObject], rax
0x1800064ef  mov     rsi, rax
0x1800064f2  mov     [rsp+1F0h+hFile], rax
0x1800064f7  mov     rdi, rcx
0x1800064fa  xor     eax, eax
0x1800064fc  mov     [rsp+1F0h+lpFileName], rcx
0x180006501  xorps   xmm1, xmm1
0x180006504  mov     dword ptr [rbp+0F0h+VirtualStorageType.VendorId.Data4+4], eax
0x18000650a  xor     edx, edx; Val
0x18000650c  mov     dword ptr [rbp+0F0h+var_130+4], eax
0x18000650f  mov     r8d, 0B4h; Size
0x180006515  mov     [rbp+0F0h+SecurityDescriptor], r9
0x180006519  lea     rcx, [rbp+0F0h+var_130]; void *
0x18000651d  mov     [rsp+1F0h+var_19F], r15b
0x180006522  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x180006526  mov     [rsp+1F0h+var_1A0], r15b
0x18000652b  movups  xmmword ptr [rbp+0F0h+P], xmm1
0x18000652f  movups  xmmword ptr [rbp+0F0h+VirtualStorageType.DeviceId], xmm0
0x180006536  call    memset_0
0x18000653b  mov     [rbp+0F0h+var_158], r15
0x18000653f  mov     dword ptr [rsp+1F0h+var_178+4], r15d
0x180006544  mov     [rbp+0F0h+Path], r15
0x180006548  mov     dword ptr [rsp+1F0h+var_178], r15d
0x18000654d  mov     rdx, cs:WPP_GLOBAL_Control
0x180006554  lea     rax, WPP_GLOBAL_Control
0x18000655b  mov     r15d, [rbp+0F0h+arg_20]
0x180006562  cmp     rdx, rax
0x180006565  jz      short loc_18000659E
0x180006567  test    byte ptr [rdx+1Ch], 20h
0x18000656b  jz      short loc_18000659E
0x18000656d  cmp     byte ptr [rdx+19h], 4
0x180006571  jb      short loc_18000659E
0x180006573  mov     ecx, r15d
0x180006576  mov     eax, r15d
0x180006579  shr     ecx, 6
0x18000657c  mov     r9, rdi
0x18000657f  and     ecx, 1
0x180006582  shr     eax, 3
0x180006585  mov     dword ptr [rsp+1F0h+Parameters], ecx; char
0x180006589  and     eax, 1
0x18000658c  mov     rcx, [rdx+10h]; LoggerHandle
0x180006590  mov     [rsp+1F0h+ProviderSpecificFlags], eax; char
0x180006594  mov     qword ptr [rsp+1F0h+Flags], r12; __int64
0x180006599  call    WPP_SF_SZdd
0x18000659e  mov     rax, [rsp+1F0h+var_190]
0x1800065a3  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x1800065a7  mov     r12d, r15d
0x1800065aa  mov     rdx, rdi; SourceString
0x1800065ad  and     r12d, 40h
0x1800065b1  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800065b8  call    cs:__imp_RtlInitUnicodeString
0x1800065bf  nop     dword ptr [rax+rax+00h]
0x1800065c4  cmp     dword ptr [rbx], 3
0x1800065c7  jl      short loc_1800065E5
0x1800065c9  movups  xmm0, xmmword ptr [rbx+88h]
0x1800065d0  mov     eax, [rbx+98h]
0x1800065d6  mov     dword ptr [rbp+0F0h+VirtualStorageType.VendorId.Data4+4], eax
0x1800065dc  movups  xmmword ptr [rbp+0F0h+VirtualStorageType.DeviceId], xmm0
0x1800065e3  jmp     short loc_1800065FE
0x1800065e5  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x1800065ec  mov     [rbp+0F0h+VirtualStorageType.DeviceId], 3
0x1800065f6  movdqu  xmmword ptr [rbp+0F0h+VirtualStorageType.VendorId.Data1], xmm0
0x1800065fe  movups  xmm0, xmmword ptr [rbx+10h]
0x180006602  mov     rax, [rbx+0B0h]
0x180006609  movups  xmm1, xmmword ptr [rbx+20h]
0x18000660d  mov     qword ptr [rbp+0F0h+var_130.8+0A8h], rax
0x180006611  movups  xmm2, xmmword ptr [rbx]
0x180006614  movups  xmmword ptr [rbp+0F0h+var_130.8+8], xmm0
0x180006618  movups  xmm0, xmmword ptr [rbx+30h]
0x18000661c  movups  xmmword ptr [rbp+0F0h+var_130.8+18h], xmm1
0x180006620  movups  xmm1, xmmword ptr [rbx+40h]
0x180006624  movups  xmmword ptr [rbp+0F0h+var_130.8+28h], xmm0
0x180006628  movups  xmm0, xmmword ptr [rbx+50h]
0x18000662c  movups  xmmword ptr [rbp+0F0h+var_130.8+38h], xmm1
0x180006630  movups  xmm1, xmmword ptr [rbx+60h]
0x180006634  movups  xmmword ptr [rbp+0F0h+var_130.8+48h], xmm0
0x180006638  movups  xmm0, xmmword ptr [rbx+70h]
0x18000663c  movups  xmmword ptr [rbp+0F0h+var_130.8+58h], xmm1
0x180006640  movups  xmm1, xmmword ptr [rbx+80h]
0x180006647  movups  xmmword ptr [rbp+0F0h+var_130.8+68h], xmm0
0x18000664b  movups  xmm0, xmmword ptr [rbx+90h]
0x180006652  movups  xmmword ptr [rbp+0F0h+var_130.8+78h], xmm1
0x180006656  movups  xmm1, xmmword ptr [rbx+0A0h]
0x18000665d  movd    eax, xmm2
0x180006661  movups  xmmword ptr [rbp+0F0h+var_130.8+88h], xmm0
0x180006665  movaps  xmmword ptr [rbp+0F0h+var_130.Version], xmm2
0x180006669  movups  xmmword ptr [rbp+0F0h+var_130.8+98h], xmm1
0x18000666d  cmp     eax, 2
0x180006670  jz      short loc_180006677
0x180006672  cmp     eax, 3
0x180006675  jl      short loc_18000667B
0x180006677  and     dword ptr [rbp+0F0h+var_130.8+38h], 0FFFFFFBFh
0x18000667b  lea     rax, [rsp+1F0h+var_178]
0x180006680  mov     rcx, rdi; Str
0x180006683  mov     qword ptr [rsp+1F0h+ProviderSpecificFlags], rax; __int64
0x180006688  lea     r9, [rsp+1F0h+var_178+4]
0x18000668d  lea     rax, [rbp+0F0h+Path]
0x180006691  lea     r8, [rbp+0F0h+var_158]
0x180006695  mov     qword ptr [rsp+1F0h+Flags], rax; __int64
0x18000669a  call    GetBackingFilePath
0x18000669f  mov     rdi, [rbp+0F0h+Path]
0x1800066a3  mov     ebx, eax
0x1800066a5  test    eax, eax
0x1800066a7  jnz     loc_1800068F5
0x1800066ad  test    r14, r14
0x1800066b0  jnz     short loc_180006719
0x1800066b2  mov     r9, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1800066b6  lea     rax, [rsp+1F0h+hObject]
0x1800066bb  mov     [rsp+1F0h+Handle], rax; Handle
0x1800066c0  mov     ecx, r15d
0x1800066c3  lea     rax, [rbp+0F0h+var_130]
0x1800066c7  mov     [rsp+1F0h+Overlapped], r14; Overlapped
0x1800066cc  mov     [rsp+1F0h+Parameters], rax; Parameters
0x1800066d1  and     ecx, 0FFFFFFBDh
0x1800066d4  mov     eax, [rbp+0F0h+arg_28]
0x1800066da  mov     r8d, r13d; VirtualDiskAccessMask
0x1800066dd  mov     [rsp+1F0h+ProviderSpecificFlags], eax; ProviderSpecificFlags
0x1800066e1  mov     rdx, rdi; Path
0x1800066e4  mov     [rsp+1F0h+Flags], ecx; Flags
0x1800066e8  lea     rcx, [rbp+0F0h+VirtualStorageType]; VirtualStorageType
0x1800066ef  call    CreateVirtualDisk
0x1800066f4  mov     ebx, eax
0x1800066f6  test    eax, eax
0x1800066f8  jnz     loc_1800068F5
0x1800066fe  mov     rcx, [rsp+1F0h+hObject]; hObject
0x180006703  mov     [rsp+1F0h+var_19F], 1
0x180006708  call    cs:__imp_CloseHandle
0x18000670f  nop     dword ptr [rax+rax+00h]
0x180006714  jmp     loc_180006880
0x180006719  test    r12d, r12d
0x18000671c  jz      loc_1800067DD
0x180006722  mov     rcx, cs:WPP_GLOBAL_Control
0x180006729  lea     r13, WPP_GLOBAL_Control
0x180006730  cmp     rcx, r13
0x180006733  jz      short loc_180006757
0x180006735  test    byte ptr [rcx+1Ch], 20h
0x180006739  jz      short loc_180006757
0x18000673b  cmp     byte ptr [rcx+19h], 4
0x18000673f  jb      short loc_180006757
0x180006741  mov     rcx, [rcx+10h]
0x180006745  mov     edx, 0Bh
0x18000674a  mov     r9, r14
0x18000674d  mov     qword ptr [rsp+1F0h+Flags], rdi
0x180006752  call    WPP_SF_SS
0x180006757  mov     rdx, rdi; lpNewFileName
0x18000675a  mov     rcx, r14; lpExistingFileName
0x18000675d  call    cs:__imp_MoveFileW
0x180006764  nop     dword ptr [rax+rax+00h]
0x180006769  test    eax, eax
0x18000676b  jnz     loc_18000687B
0x180006771  call    cs:__imp_GetLastError
0x180006778  nop     dword ptr [rax+rax+00h]
0x18000677d  mov     ebx, eax
0x18000677f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006786  cmp     rcx, r13
0x180006789  jz      short loc_1800067B8
0x18000678b  test    byte ptr [rcx+1Ch], 20h
0x18000678f  jz      short loc_1800067B8
0x180006791  cmp     byte ptr [rcx+19h], 2
0x180006795  jb      short loc_1800067B8
0x180006797  mov     edx, 0Ch
0x18000679c  mov     rcx, [rcx+10h]
0x1800067a0  mov     r9, r14
0x1800067a3  mov     [rsp+1F0h+ProviderSpecificFlags], eax
0x1800067a7  mov     qword ptr [rsp+1F0h+Flags], rdi
0x1800067ac  call    WPP_SF_SSd
0x1800067b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067b8  mov     r13b, [rsp+1F0h+var_1A0]
0x1800067bd  test    ebx, ebx
0x1800067bf  jnz     loc_180006901
0x1800067c5  mov     r15, [rsp+1F0h+var_190]
0x1800067ca  mov     [r15], rsi
0x1800067cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800067d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067d8  jmp     loc_180006906
0x1800067dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067e4  lea     r13, WPP_GLOBAL_Control
0x1800067eb  cmp     rcx, r13
0x1800067ee  jz      short loc_180006812
0x1800067f0  test    byte ptr [rcx+1Ch], 20h
0x1800067f4  jz      short loc_180006812
0x1800067f6  cmp     byte ptr [rcx+19h], 4
0x1800067fa  jb      short loc_180006812
0x1800067fc  mov     rcx, [rcx+10h]
0x180006800  mov     edx, 0Dh
0x180006805  mov     r9, r14
0x180006808  mov     qword ptr [rsp+1F0h+Flags], rdi
0x18000680d  call    WPP_SF_SS
0x180006812  mov     [rsp+1F0h+ProviderSpecificFlags], 8000h; dwCopyFlags
0x18000681a  xor     r9d, r9d; lpData
0x18000681d  xor     r8d, r8d; lpProgressRoutine
0x180006820  mov     qword ptr [rsp+1F0h+Flags], 0; pbCancel
0x180006829  mov     rdx, rdi; lpNewFileName
0x18000682c  mov     rcx, r14; lpExistingFileName
0x18000682f  call    cs:__imp_CopyFileExW
0x180006836  nop     dword ptr [rax+rax+00h]
0x18000683b  test    eax, eax
0x18000683d  jnz     short loc_18000687B
0x18000683f  call    cs:__imp_GetLastError
0x180006846  nop     dword ptr [rax+rax+00h]
0x18000684b  mov     ebx, eax
0x18000684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006854  cmp     rcx, r13
0x180006857  jz      loc_1800067B8
0x18000685d  test    byte ptr [rcx+1Ch], 20h
0x180006861  jz      loc_1800067B8
0x180006867  cmp     byte ptr [rcx+19h], 2
0x18000686b  jb      loc_1800067B8
0x180006871  mov     edx, 0Eh
0x180006876  jmp     loc_18000679C
0x18000687b  mov     [rsp+1F0h+var_19F], 1
0x180006880  mov     rdx, [rbp+0F0h+var_58]; __int64
0x180006887  mov     rcx, rdi; __int64
0x18000688a  call    ConvertVhdxToVhdSetRsvd
0x18000688f  mov     ebx, eax
0x180006891  test    eax, eax
0x180006893  jnz     short loc_1800068F5
0x180006895  lea     rdx, [rbp+0F0h+P]; __int64
0x180006899  mov     r13b, 1
0x18000689c  lea     rcx, [rbp+0F0h+DestinationString]; __int64
0x1800068a0  call    ConstructRsvdPathToFile
0x1800068a5  mov     ebx, eax
0x1800068a7  test    eax, eax
0x1800068a9  jnz     short loc_1800068FA
0x1800068ab  lea     r8, [rsp+1F0h+hFile]
0x1800068b0  lea     rcx, [rbp+0F0h+P]
0x1800068b4  call    OpenPathForRsvd
0x1800068b9  mov     rsi, [rsp+1F0h+hFile]
0x1800068be  mov     ebx, eax
0x1800068c0  test    eax, eax
0x1800068c2  jnz     short loc_1800068FA
0x1800068c4  test    r15b, 8
0x1800068c8  jnz     loc_1800067C5
0x1800068ce  xorps   xmm0, xmm0
0x1800068d1  lea     rdx, [rbp+0F0h+var_58]
0x1800068d8  mov     rcx, rsi; hFile
0x1800068db  movups  xmmword ptr [rbp+0F0h+var_58], xmm0
0x1800068e2  call    DeleteVhdSetSnapshotRsvd
0x1800068e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ee  mov     ebx, eax
0x1800068f0  jmp     loc_1800067BD
0x1800068f5  mov     r13b, [rsp+1F0h+var_1A0]
0x1800068fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006901  mov     r15, [rsp+1F0h+var_190]
0x180006906  cmp     [rbp+0F0h+P+8], 0
0x18000690b  jz      short loc_180006933
0x18000690d  mov     rcx, gs:60h
0x180006916  xor     edx, edx; Flags
0x180006918  mov     r8, [rbp+0F0h+P+8]; P
0x18000691c  mov     rcx, [rcx+30h]; HeapHandle
0x180006920  call    cs:__imp_RtlFreeHeap
0x180006927  nop     dword ptr [rax+rax+00h]
0x18000692c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006933  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180006937  jz      short loc_18000694F
0x180006939  mov     rcx, rsi; hObject
0x18000693c  call    cs:__imp_CloseHandle
0x180006943  nop     dword ptr [rax+rax+00h]
0x180006948  mov     rcx, cs:WPP_GLOBAL_Control
0x18000694f  test    ebx, ebx
0x180006951  jz      loc_180006A48
0x180006957  test    r13b, r13b
0x18000695a  jz      short loc_1800069D0
0x18000695c  test    r12d, r12d
0x18000695f  jz      loc_180006A24
0x180006965  mov     rdx, r14; lpNewFileName
0x180006968  mov     rcx, rdi; lpExistingFileName
0x18000696b  call    cs:__imp_MoveFileW
0x180006972  nop     dword ptr [rax+rax+00h]
0x180006977  test    eax, eax
0x180006979  jnz     short loc_1800069C9
0x18000697b  call    cs:__imp_GetLastError
0x180006982  nop     dword ptr [rax+rax+00h]
0x180006987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000698e  lea     r12, WPP_GLOBAL_Control
0x180006995  cmp     rcx, r12
0x180006998  jz      short loc_1800069D7
  ... truncated ...
```
