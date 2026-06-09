# HrResizeMarshalID(ushort,ulong)

- ea: `0x18001b434`
- end: `0x18001b6db`
- name: `?HrResizeMarshalID@@YAJGK@Z`
- size: `679`
- prototype: `int(unsigned __int16, unsigned int)`
- caller_count: `7`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800178b0`
- `0x180018660`
- `0x18001a888`
- `0x18001a950`
- `0x18002e1b0`
- `0x18002f230`
- `0x18002f4d0`

## callees

- `0x180002556`
- `0x180004370`
- `0x18000ae04`
- `0x18001acd8`
- `0x18001b080`
- `0x18001b1d0`
- `0x18001b434`
- `0x18001b738`
- `0x18001b7d0`
- `0x18001b8c4`
- `0x18001ba6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b543`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b575`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b575`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001b531`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001b531`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b5a4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b5a4`

## pseudocode

```c
__int64 __fastcall HrResizeMarshalID(unsigned __int16 a1, DWORD a2)
{
  unsigned int v2; // r13d
  int v5; // eax
  struct _MID_KEY *v6; // rdi
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE FileMappingW; // r15
  unsigned int v11; // r14d
  void *v12; // rax
  size_t v13; // r8
  int LastErrorHRESULT; // eax
  unsigned int v15; // eax
  int v16; // eax
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-48h]
  unsigned int v18; // [rsp+90h] [rbp+8h] BYREF
  struct _MID_KEY *v19; // [rsp+A0h] [rbp+18h] BYREF
  void *Src; // [rsp+A8h] [rbp+20h] BYREF

  v2 = a1;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  v19 = 0;
  v5 = HrMapMarshalIDKey(a1, &v19, 0);
  v6 = v19;
  v7 = v5;
  if ( v19 )
  {
    Src = 0;
    v18 = 0;
    v7 = HrMapMarshalIDData(v19, &Src, &v18);
    if ( v7 < 0 )
    {
LABEL_35:
      HrUnmapMarshalIDKey(v6);
      goto LABEL_36;
    }
    LODWORD(v19) = 0;
    FileMappingW = 0;
    v11 = v18;
    if ( a2 && v18 != a2 )
    {
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, a2, 0);
      if ( FileMappingW )
      {
        LODWORD(v19) = GetCurrentProcessId();
        if ( !Src )
          goto LABEL_25;
        v12 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
        lpBaseAddress = v12;
        if ( v12 )
        {
          v13 = v11;
          if ( a2 < v11 )
            v13 = a2;
          memcpy_0(v12, Src, v13);
          UnmapViewOfFile(lpBaseAddress);
        }
        else
        {
          LastErrorHRESULT = GetLastErrorHRESULT();
          v7 = LastErrorHRESULT;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v9, FileMappingW, LastErrorHRESULT);
        }
      }
      else
      {
        v15 = GetLastErrorHRESULT();
        v7 = v15;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, v15);
      }
    }
    if ( Src )
      HrUnmapMarshalIDData(Src);
    if ( v7 < 0 )
      goto LABEL_31;
LABEL_25:
    if ( *(_QWORD *)v6 && v11 != a2 )
    {
      v7 = HrDuplicateHandle(*(HANDLE *)v6, *((_DWORD *)v6 + 2), 0, 1);
      if ( v7 < 0 )
      {
LABEL_31:
        if ( v11 != a2 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_DddD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v2, v11, a2, v7);
        goto LABEL_35;
      }
      *(_OWORD *)v6 = 0;
    }
    if ( FileMappingW )
    {
      v16 = (int)v19;
      *(_QWORD *)v6 = FileMappingW;
      *((_DWORD *)v6 + 2) = v16;
      *((_DWORD *)v6 + 3) = a2;
    }
    goto LABEL_31;
  }
LABEL_36:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      &WPP_57b06483306a3a4d34d88419a088456d_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b434  push    rbx
0x18001b436  push    rbp
0x18001b437  push    rsi
0x18001b438  push    rdi
0x18001b439  push    r13
0x18001b43b  push    r14
0x18001b43d  push    r15
0x18001b43f  sub     rsp, 50h
0x18001b443  movzx   r13d, cx
0x18001b447  xor     r14d, r14d
0x18001b44a  mov     esi, edx
0x18001b44c  test    r13w, r13w
0x18001b450  jnz     short loc_18001B48F
0x18001b452  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b459  lea     rbp, WPP_GLOBAL_Control
0x18001b460  cmp     rcx, rbp
0x18001b463  jz      short loc_18001B485
0x18001b465  test    byte ptr [rcx+1Ch], 4
0x18001b469  jz      short loc_18001B485
0x18001b46b  mov     rcx, [rcx+10h]
0x18001b46f  lea     edx, [r14+22h]
0x18001b473  mov     r9d, 80070057h
0x18001b479  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001b480  call    WPP_SF_d
0x18001b485  mov     eax, 80070057h
0x18001b48a  jmp     loc_18001B6CC
0x18001b48f  xor     r8d, r8d; int
0x18001b492  mov     [rsp+88h+arg_10], r14
0x18001b49a  lea     rdx, [rsp+88h+arg_10]; struct _MID_KEY **
0x18001b4a2  movzx   ecx, r13w; unsigned __int16
0x18001b4a6  call    ?HrMapMarshalIDKey@@YAJGPEAPEAU_MID_KEY@@H@Z; HrMapMarshalIDKey(ushort,_MID_KEY * *,int)
0x18001b4ab  mov     rdi, [rsp+88h+arg_10]
0x18001b4b3  lea     rbp, WPP_GLOBAL_Control
0x18001b4ba  mov     ebx, eax
0x18001b4bc  test    rdi, rdi
0x18001b4bf  jz      loc_18001B6A0
0x18001b4c5  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x18001b4cd  mov     [rsp+88h+Src], r14
0x18001b4d5  lea     rdx, [rsp+88h+Src]; void **
0x18001b4dd  mov     [rsp+88h+arg_0], r14d
0x18001b4e5  mov     rcx, rdi; struct _MID_KEY *
0x18001b4e8  call    ?HrMapMarshalIDData@@YAJPEAU_MID_KEY@@PEAPEAXPEAK@Z; HrMapMarshalIDData(_MID_KEY *,void * *,ulong *)
0x18001b4ed  mov     ebx, eax
0x18001b4ef  test    eax, eax
0x18001b4f1  js      loc_18001B698
0x18001b4f7  mov     dword ptr [rsp+88h+arg_10], r14d
0x18001b4ff  mov     r15, r14
0x18001b502  mov     r14d, [rsp+88h+arg_0]
0x18001b50a  test    esi, esi
0x18001b50c  jz      loc_18001B60D
0x18001b512  cmp     r14d, esi
0x18001b515  jz      loc_18001B60D
0x18001b51b  xor     r9d, r9d; dwMaximumSizeHigh
0x18001b51e  mov     [rsp+88h+lpName], r15; lpName
0x18001b523  xor     edx, edx; lpFileMappingAttributes
0x18001b525  mov     [rsp+88h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18001b529  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001b52d  lea     r8d, [r9+4]; flProtect
0x18001b531  call    cs:__imp_CreateFileMappingW
0x18001b537  mov     r15, rax
0x18001b53a  test    rax, rax
0x18001b53d  jz      loc_18001B5DC
0x18001b543  call    cs:__imp_GetCurrentProcessId
0x18001b549  cmp     [rsp+88h+Src], 0
0x18001b552  mov     dword ptr [rsp+88h+arg_10], eax
0x18001b559  jz      loc_18001B629
0x18001b55f  xor     r9d, r9d; dwFileOffsetLow
0x18001b562  mov     qword ptr [rsp+88h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001b56b  xor     r8d, r8d; dwFileOffsetHigh
0x18001b56e  mov     rcx, r15; hFileMappingObject
0x18001b571  lea     edx, [r9+2]; dwDesiredAccess
0x18001b575  call    cs:__imp_MapViewOfFile
0x18001b57b  mov     [rsp+88h+lpBaseAddress], rax
0x18001b580  test    rax, rax
0x18001b583  jz      short loc_18001B5AC
0x18001b585  mov     rdx, [rsp+88h+Src]; Src
0x18001b58d  mov     r8d, r14d
0x18001b590  cmp     esi, r14d
0x18001b593  mov     rcx, rax; void *
0x18001b596  cmovb   r8d, esi; Size
0x18001b59a  call    memcpy_0
0x18001b59f  mov     rcx, [rsp+88h+lpBaseAddress]; lpBaseAddress
0x18001b5a4  call    cs:__imp_UnmapViewOfFile
0x18001b5aa  jmp     short loc_18001B60D
0x18001b5ac  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001b5b1  mov     ebx, eax
0x18001b5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5ba  cmp     rcx, rbp
0x18001b5bd  jz      short loc_18001B60D
0x18001b5bf  test    byte ptr [rcx+1Ch], 4
0x18001b5c3  jz      short loc_18001B60D
0x18001b5c5  mov     rcx, [rcx+10h]
0x18001b5c9  mov     edx, 23h ; '#'
0x18001b5ce  mov     r9, r15
0x18001b5d1  mov     [rsp+88h+dwMaximumSizeLow], eax
0x18001b5d5  call    WPP_SF_qD
0x18001b5da  jmp     short loc_18001B60D
0x18001b5dc  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001b5e1  mov     ebx, eax
0x18001b5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5ea  cmp     rcx, rbp
0x18001b5ed  jz      short loc_18001B60D
0x18001b5ef  test    byte ptr [rcx+1Ch], 4
0x18001b5f3  jz      short loc_18001B60D
0x18001b5f5  mov     rcx, [rcx+10h]
0x18001b5f9  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001b600  mov     edx, 24h ; '$'
0x18001b605  mov     r9d, eax
0x18001b608  call    WPP_SF_d
0x18001b60d  cmp     [rsp+88h+Src], 0
0x18001b616  jz      short loc_18001B625
0x18001b618  mov     rcx, [rsp+88h+Src]; void *
0x18001b620  call    ?HrUnmapMarshalIDData@@YAJPEAX@Z; HrUnmapMarshalIDData(void *)
0x18001b625  test    ebx, ebx
0x18001b627  js      short loc_18001B668
0x18001b629  mov     rcx, [rdi]; hSourceHandle
0x18001b62c  test    rcx, rcx
0x18001b62f  jz      short loc_18001B653
0x18001b631  cmp     r14d, esi
0x18001b634  jz      short loc_18001B653
0x18001b636  mov     edx, [rdi+8]; dwProcessId
0x18001b639  mov     r9d, 1; int
0x18001b63f  xor     r8d, r8d; void **
0x18001b642  call    ?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z; HrDuplicateHandle(void *,ulong,void * *,int)
0x18001b647  mov     ebx, eax
0x18001b649  test    eax, eax
0x18001b64b  js      short loc_18001B668
0x18001b64d  xorps   xmm0, xmm0
0x18001b650  movups  xmmword ptr [rdi], xmm0
0x18001b653  test    r15, r15
0x18001b656  jz      short loc_18001B668
0x18001b658  mov     eax, dword ptr [rsp+88h+arg_10]
0x18001b65f  mov     [rdi], r15
0x18001b662  mov     [rdi+8], eax
0x18001b665  mov     [rdi+0Ch], esi
0x18001b668  cmp     r14d, esi
0x18001b66b  jz      short loc_18001B698
0x18001b66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b674  cmp     rcx, rbp
0x18001b677  jz      short loc_18001B698
0x18001b679  test    byte ptr [rcx+1Ch], 8
0x18001b67d  jz      short loc_18001B698
0x18001b67f  mov     rcx, [rcx+10h]
0x18001b683  mov     r9d, r13d
0x18001b686  mov     [rsp+88h+var_58], ebx
0x18001b68a  mov     dword ptr [rsp+88h+lpName], esi
0x18001b68e  mov     [rsp+88h+dwMaximumSizeLow], r14d
0x18001b693  call    WPP_SF_DddD
0x18001b698  mov     rcx, rdi; struct _MID_KEY *
0x18001b69b  call    ?HrUnmapMarshalIDKey@@YAJPEAU_MID_KEY@@@Z; HrUnmapMarshalIDKey(_MID_KEY *)
0x18001b6a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6a7  cmp     rcx, rbp
0x18001b6aa  jz      short loc_18001B6CA
0x18001b6ac  test    byte ptr [rcx+1Ch], 10h
0x18001b6b0  jz      short loc_18001B6CA
0x18001b6b2  mov     rcx, [rcx+10h]
0x18001b6b6  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001b6bd  mov     edx, 26h ; '&'
0x18001b6c2  mov     r9d, ebx
0x18001b6c5  call    WPP_SF_d
0x18001b6ca  mov     eax, ebx
0x18001b6cc  add     rsp, 50h
0x18001b6d0  pop     r15
0x18001b6d2  pop     r14
0x18001b6d4  pop     r13
0x18001b6d6  pop     rdi
0x18001b6d7  pop     rsi
0x18001b6d8  pop     rbp
0x18001b6d9  pop     rbx
0x18001b6da  retn
```
