# WIMCommitImageChanges

- ea: `0x18000ed20`
- end: `0x18000f11b`
- name: `WIMCommitImageChanges`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f278`

## callees

- `0x18000d9c4`
- `0x18000daf0`
- `0x18000ed20`
- `0x180011880`
- `0x180011a38`
- `0x180011a84`
- `0x180011b50`
- `0x180011bb8`
- `0x180011be8`
- `0x18001219c`
- `0x180012208`
- `0x180012304`
- `0x180012368`
- `0x1800130c0`
- `0x180013490`
- `0x180013878`
- `0x180015e50`
- `0x180016178`
- `0x180017344`
- `0x180017c14`
- `0x180017d94`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ef4b`
- `KERNEL32!GetLastError` at `0x18000effe`
- `KERNEL32!GetLastError` at `0x18000ef4b`
- `KERNEL32!GetLastError` at `0x18000effe`
- `KERNEL32!SetLastError` at `0x18000ed67`
- `KERNEL32!SetLastError` at `0x18000f0f3`
- `KERNEL32!SetLastError` at `0x18000ed67`
- `KERNEL32!SetLastError` at `0x18000f0f3`
- `KERNEL32!LocalFree` at `0x18000ee18`
- `KERNEL32!LocalFree` at `0x18000ee18`

## string_xrefs

- `0x18000eefe`: `WIMCommitImageChanges`
- `0x18000f02b`: `UpdateWIMHeader failed`

## pseudocode

```c
__int64 __fastcall WIMCommitImageChanges(__int64 a1)
{
  __int64 v1; // rbx
  BOOL v3; // ebp
  DWORD LastError; // r14d
  __int64 WimHeader; // rax
  __int64 v7; // rax
  int v8; // edx
  __int64 *v9; // rax
  BOOL i; // r8d
  bool v11; // zf
  __int64 v12; // rax
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // edx
  int WimPath; // eax
  NTSTATUS Status; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  NTSTATUS v21; // edx
  __int64 v22; // rax
  __int64 WimLastEOF; // rax
  void *WimFileHandle; // rax
  LARGE_INTEGER v25; // rdx
  __int64 v26; // r8
  DWORD v27; // r9d
  void *v28; // rax
  unsigned int v29; // [rsp+70h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  v3 = 1;
  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -17960958 )
    {
      v1 = *(_QWORD *)(a1 + 8);
    }
    else if ( *(_DWORD *)a1 == -17960959 )
    {
      v1 = a1;
    }
  }
  LastError = 0;
  if ( !a1 )
  {
    SetLastError(6u);
    return 0;
  }
  if ( *(_QWORD *)(a1 + 64) || !v1 )
    return 1;
  if ( (GetHandleFlags(a1) & 1) != 0
    && (GetHandleFlags(v1) & 0x11) == 0
    && ((GetHandleFlags(v1) & 2) != 0 || (GetHandleFlags(v1) & 4) != 0) )
  {
    hMem = 0;
    v29 = 0;
    if ( (unsigned int)WIMGetImageInformation(a1, &hMem, &v29) )
    {
      if ( !hMem )
        goto LABEL_20;
      if ( v29 >= 2 )
        v3 = WIMSetImageInformation(a1, hMem) != 0;
    }
    if ( hMem )
      LocalFree(hMem);
LABEL_20:
    if ( !(unsigned int)GetBootIndex(v1) )
    {
      *(_DWORD *)(GetWimHeader(v1) + 240) = 0;
      WimHeader = GetWimHeader(v1);
      memset_0((void *)(WimHeader + 176), 0, 0x40u);
    }
    if ( *(_QWORD *)(v1 + 16) && !*(_QWORD *)(v1 + 496) )
      GetWimHeader(v1);
    GetWimHeader(v1);
    v7 = GetWimHeader(v1);
    *(_DWORD *)(v7 + 16) = v8;
    v9 = *(__int64 **)(v1 + 16);
    if ( v9 && *(_QWORD *)(v1 + 496) )
    {
      for ( i = 0; v9 && !i; i = v11 )
      {
        v11 = (*((_BYTE *)v9 + 15) & 2) == 0;
        v9 = (__int64 *)*v9;
      }
      GetWimHeader(v1);
      v12 = GetWimHeader(v1);
      if ( v14 )
        v15 = v13 & 0xFFFFFFDF;
      else
        v15 = v13 | 0x20;
      *(_DWORD *)(v12 + 16) = v15;
    }
    if ( !v3 )
      goto LABEL_55;
    if ( (unsigned int)SaveOffsetTable(a1)
      && (unsigned int)SaveXmlInformation(a1)
      && (unsigned int)GenerateIntegrityInfo(v1)
      && (unsigned int)SaveIntegrityInfo(v1) )
    {
      ResetHandleFlag(v1, 16);
      ResetHandleFlag(v1, 6);
    }
    else
    {
      v3 = 0;
      LastError = GetLastError();
      WimPath = GetWimPath(v1);
      WIMLogMsg(1, a1, WimPath, (int)L"SaveOffset failed", Status, (__int64)L"WIMCommitImageChanges", 2284);
    }
    if ( !v3 )
      goto LABEL_55;
    if ( !(unsigned int)UpdateWimHeader(v1, 0) )
    {
      v3 = 0;
      LastError = GetLastError();
      v20 = GetWimPath(v1);
      WIMLogMsg(1, a1, v20, (int)L"UpdateWIMHeader failed", v21, (__int64)L"WIMCommitImageChanges", 2312);
LABEL_52:
      if ( v3 )
      {
        if ( (GetHandleFlags(v1) & 0x100) != 0 )
        {
          v22 = GetWimHeader(v1);
          SetWriteOffset(v1, *(_QWORD *)(v22 + 64));
        }
        goto LABEL_56;
      }
LABEL_55:
      SetHandleFlag(v1, 16);
LABEL_56:
      ResetHandleFlag(v1, 14);
      goto LABEL_57;
    }
    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(v1, 0, (LARGE_INTEGER)g_liZero.QuadPart);
    if ( *(_DWORD *)v1 == -17960958 )
    {
      v19 = *(_QWORD *)(v1 + 8);
    }
    else
    {
      if ( *(_DWORD *)v1 != -17960959 )
      {
LABEL_50:
        ResetHandleFlag(v1, 8);
        ResetHandleFlag(a1, 1);
        goto LABEL_52;
      }
      v19 = v1;
    }
    if ( v19 )
      *(_QWORD *)(v19 + 560) = v18;
    goto LABEL_50;
  }
LABEL_57:
  if ( (GetHandleFlags(v1) & 1) == 0 && (GetHandleFlags(v1) & 0x10) != 0 )
  {
    WimLastEOF = GetWimLastEOF(v1);
    SetWriteOffset(v1, WimLastEOF);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(v1, 0, (LARGE_INTEGER)g_liZero.QuadPart);
    WimFileHandle = (void *)GetWimFileHandle(v1);
    WIMSetFilePointerEx(WimFileHandle, v25, v26, v27);
    v28 = (void *)GetWimFileHandle(v1);
    WIMSetEndOfFile(v28);
  }
  if ( LastError )
    SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x18000ed20  mov     [rsp+arg_10], rbx
0x18000ed25  push    rbp
0x18000ed26  push    rdi
0x18000ed27  push    r12
0x18000ed29  push    r13
0x18000ed2b  push    r14
0x18000ed2d  sub     rsp, 40h
0x18000ed31  xor     ebx, ebx
0x18000ed33  mov     r12d, 1
0x18000ed39  mov     rdi, rcx
0x18000ed3c  mov     ebp, r12d
0x18000ed3f  test    rcx, rcx
0x18000ed42  jz      short loc_18000ED5C
0x18000ed44  cmp     dword ptr [rcx], 0FEEDF002h
0x18000ed4a  jnz     short loc_18000ED52
0x18000ed4c  mov     rbx, [rcx+8]
0x18000ed50  jmp     short loc_18000ED5C
0x18000ed52  cmp     dword ptr [rcx], 0FEEDF001h
0x18000ed58  cmovz   rbx, rdi
0x18000ed5c  xor     r14d, r14d
0x18000ed5f  test    rdi, rdi
0x18000ed62  jnz     short loc_18000ED7A
0x18000ed64  lea     ecx, [rdi+6]; dwErrCode
0x18000ed67  call    cs:__imp_SetLastError
0x18000ed6e  nop     dword ptr [rax+rax+00h]
0x18000ed73  xor     eax, eax
0x18000ed75  jmp     loc_18000F106
0x18000ed7a  cmp     [rcx+40h], r14
0x18000ed7e  jnz     loc_18000F103
0x18000ed84  test    rbx, rbx
0x18000ed87  jz      loc_18000F103
0x18000ed8d  call    GetHandleFlags
0x18000ed92  test    r12b, al
0x18000ed95  jz      loc_18000F08B
0x18000ed9b  mov     rcx, rbx
0x18000ed9e  call    GetHandleFlags
0x18000eda3  test    al, 11h
0x18000eda5  jnz     loc_18000F08B
0x18000edab  mov     rcx, rbx
0x18000edae  call    GetHandleFlags
0x18000edb3  test    al, 2
0x18000edb5  jnz     short loc_18000EDC7
0x18000edb7  mov     rcx, rbx
0x18000edba  call    GetHandleFlags
0x18000edbf  test    al, 4
0x18000edc1  jz      loc_18000F08B
0x18000edc7  and     [rsp+68h+hMem], r14
0x18000edcc  lea     r8, [rsp+68h+arg_0]
0x18000edd1  and     [rsp+68h+arg_0], r14d
0x18000edd6  lea     rdx, [rsp+68h+hMem]
0x18000eddb  mov     rcx, rdi
0x18000edde  call    WIMGetImageInformation
0x18000ede3  test    eax, eax
0x18000ede5  jz      short loc_18000EE0C
0x18000ede7  cmp     [rsp+68h+hMem], r14
0x18000edec  jz      short loc_18000EE24
0x18000edee  mov     r8d, [rsp+68h+arg_0]
0x18000edf3  cmp     r8d, 2
0x18000edf7  jb      short loc_18000EE0C
0x18000edf9  mov     rdx, [rsp+68h+hMem]
0x18000edfe  mov     rcx, rdi
0x18000ee01  call    WIMSetImageInformation
0x18000ee06  neg     eax
0x18000ee08  sbb     edx, edx
0x18000ee0a  and     ebp, edx
0x18000ee0c  cmp     [rsp+68h+hMem], r14
0x18000ee11  jz      short loc_18000EE24
0x18000ee13  mov     rcx, [rsp+68h+hMem]; hMem
0x18000ee18  call    cs:__imp_LocalFree
0x18000ee1f  nop     dword ptr [rax+rax+00h]
0x18000ee24  mov     rcx, rbx
0x18000ee27  call    GetBootIndex
0x18000ee2c  test    eax, eax
0x18000ee2e  jnz     short loc_18000EE59
0x18000ee30  mov     rcx, rbx
0x18000ee33  call    GetWimHeader
0x18000ee38  mov     rcx, rbx
0x18000ee3b  and     [rax+0F0h], r14d
0x18000ee42  call    GetWimHeader
0x18000ee47  xor     edx, edx; Val
0x18000ee49  lea     rcx, [rax+0B0h]; void *
0x18000ee50  lea     r8d, [rdx+40h]; Size
0x18000ee54  call    memset_0
0x18000ee59  cmp     [rbx+10h], r14
0x18000ee5d  jz      short loc_18000EE86
0x18000ee5f  cmp     [rbx+1F0h], r14
0x18000ee66  jnz     short loc_18000EE86
0x18000ee68  mov     rcx, rbx
0x18000ee6b  call    GetWimHeader
0x18000ee70  test    byte ptr [rax+10h], 8
0x18000ee74  jnz     short loc_18000EE86
0x18000ee76  mov     rcx, rbx
0x18000ee79  call    GetWimHeader
0x18000ee7e  mov     edx, [rax+10h]
0x18000ee81  or      edx, 10h
0x18000ee84  jmp     short loc_18000EE94
0x18000ee86  mov     rcx, rbx
0x18000ee89  call    GetWimHeader
0x18000ee8e  mov     edx, [rax+10h]
0x18000ee91  and     edx, 0FFFFFFEFh
0x18000ee94  mov     rcx, rbx
0x18000ee97  call    GetWimHeader
0x18000ee9c  mov     [rax+10h], edx
0x18000ee9f  mov     rax, [rbx+10h]
0x18000eea3  test    rax, rax
0x18000eea6  jz      short loc_18000EEEE
0x18000eea8  cmp     [rbx+1F0h], r14
0x18000eeaf  jz      short loc_18000EEEE
0x18000eeb1  xor     r8d, r8d
0x18000eeb4  jmp     short loc_18000EEC6
0x18000eeb6  test    r8d, r8d
0x18000eeb9  jnz     short loc_18000EECB
0x18000eebb  test    byte ptr [rax+0Fh], 2
0x18000eebf  mov     rax, [rax]
0x18000eec2  cmovz   r8d, r12d
0x18000eec6  test    rax, rax
0x18000eec9  jnz     short loc_18000EEB6
0x18000eecb  mov     rcx, rbx
0x18000eece  call    GetWimHeader
0x18000eed3  mov     rcx, rbx
0x18000eed6  mov     edx, [rax+10h]
0x18000eed9  call    GetWimHeader
0x18000eede  test    r8d, r8d
0x18000eee1  jnz     short loc_18000EEE8
0x18000eee3  or      edx, 20h
0x18000eee6  jmp     short loc_18000EEEB
0x18000eee8  and     edx, 0FFFFFFDFh
0x18000eeeb  mov     [rax+10h], edx
0x18000eeee  test    ebp, ebp
0x18000eef0  jz      loc_18000F071
0x18000eef6  mov     rcx, rdi
0x18000eef9  call    SaveOffsetTable
0x18000eefe  lea     r13, aWimcommitimage; "WIMCommitImageChanges"
0x18000ef05  test    eax, eax
0x18000ef07  jz      short loc_18000EF49
0x18000ef09  mov     rcx, rdi
0x18000ef0c  call    SaveXmlInformation
0x18000ef11  test    eax, eax
0x18000ef13  jz      short loc_18000EF49
0x18000ef15  mov     rcx, rbx
0x18000ef18  call    GenerateIntegrityInfo
0x18000ef1d  test    eax, eax
0x18000ef1f  jz      short loc_18000EF49
0x18000ef21  mov     rcx, rbx
0x18000ef24  call    SaveIntegrityInfo
0x18000ef29  test    eax, eax
0x18000ef2b  jz      short loc_18000EF49
0x18000ef2d  mov     edx, 10h
0x18000ef32  mov     rcx, rbx
0x18000ef35  call    ResetHandleFlag
0x18000ef3a  mov     edx, 6
0x18000ef3f  mov     rcx, rbx
0x18000ef42  call    ResetHandleFlag
0x18000ef47  jmp     short loc_18000EF96
0x18000ef49  xor     ebp, ebp
0x18000ef4b  call    cs:__imp_GetLastError
0x18000ef52  nop     dword ptr [rax+rax+00h]
0x18000ef57  movzx   edx, ax
0x18000ef5a  mov     rcx, rbx
0x18000ef5d  or      edx, 80070000h
0x18000ef63  mov     r14d, eax
0x18000ef66  test    eax, eax
0x18000ef68  cmovle  edx, eax
0x18000ef6b  call    GetWimPath
0x18000ef70  mov     [rsp+68h+var_38], 8ECh; int
0x18000ef78  lea     r9, aSaveoffsetFail; "SaveOffset failed"
0x18000ef7f  mov     [rsp+68h+var_40], r13; __int64
0x18000ef84  mov     r8, rax; int
0x18000ef87  mov     [rsp+68h+Status], edx; Status
0x18000ef8b  mov     ecx, r12d; int
0x18000ef8e  mov     rdx, rdi; int
0x18000ef91  call    _WIMLogMsg
0x18000ef96  test    ebp, ebp
0x18000ef98  jz      loc_18000F071
0x18000ef9e  xor     edx, edx
0x18000efa0  mov     rcx, rbx
0x18000efa3  call    UpdateWimHeader
0x18000efa8  test    eax, eax
0x18000efaa  jz      short loc_18000EFFC
0x18000efac  mov     r8, qword ptr cs:g_liZero
0x18000efb3  xor     edx, edx
0x18000efb5  mov     rcx, rbx
0x18000efb8  call    GetWriteOffset
0x18000efbd  cmp     dword ptr [rbx], 0FEEDF002h
0x18000efc3  jnz     short loc_18000EFCB
0x18000efc5  mov     rcx, [rbx+8]
0x18000efc9  jmp     short loc_18000EFD6
0x18000efcb  cmp     dword ptr [rbx], 0FEEDF001h
0x18000efd1  jnz     short loc_18000EFE2
0x18000efd3  mov     rcx, rbx
0x18000efd6  test    rcx, rcx
0x18000efd9  jz      short loc_18000EFE2
0x18000efdb  mov     [rcx+230h], rax
0x18000efe2  mov     edx, 8
0x18000efe7  mov     rcx, rbx
0x18000efea  call    ResetHandleFlag
0x18000efef  mov     edx, r12d
0x18000eff2  mov     rcx, rdi
0x18000eff5  call    ResetHandleFlag
0x18000effa  jmp     short loc_18000F049
0x18000effc  xor     ebp, ebp
0x18000effe  call    cs:__imp_GetLastError
0x18000f005  nop     dword ptr [rax+rax+00h]
0x18000f00a  movzx   edx, ax
0x18000f00d  mov     rcx, rbx
0x18000f010  or      edx, 80070000h
0x18000f016  mov     r14d, eax
0x18000f019  test    eax, eax
0x18000f01b  cmovle  edx, eax
0x18000f01e  call    GetWimPath
0x18000f023  mov     [rsp+68h+var_38], 908h; int
0x18000f02b  lea     r9, aUpdatewimheade; "UpdateWIMHeader failed"
0x18000f032  mov     [rsp+68h+var_40], r13; __int64
0x18000f037  mov     r8, rax; int
0x18000f03a  mov     [rsp+68h+Status], edx; Status
0x18000f03e  mov     ecx, r12d; int
0x18000f041  mov     rdx, rdi; int
0x18000f044  call    _WIMLogMsg
0x18000f049  test    ebp, ebp
0x18000f04b  jz      short loc_18000F071
0x18000f04d  mov     rcx, rbx
0x18000f050  call    GetHandleFlags
0x18000f055  bt      eax, 8
0x18000f059  jnb     short loc_18000F07E
0x18000f05b  mov     rcx, rbx
0x18000f05e  call    GetWimHeader
0x18000f063  mov     rcx, rbx
0x18000f066  mov     rdx, [rax+40h]
0x18000f06a  call    SetWriteOffset
0x18000f06f  jmp     short loc_18000F07E
0x18000f071  mov     edx, 10h
0x18000f076  mov     rcx, rbx
0x18000f079  call    SetHandleFlag
0x18000f07e  mov     edx, 0Eh
0x18000f083  mov     rcx, rbx
0x18000f086  call    ResetHandleFlag
0x18000f08b  mov     rcx, rbx
0x18000f08e  call    GetHandleFlags
0x18000f093  test    r12b, al
0x18000f096  jnz     short loc_18000F0EB
0x18000f098  mov     rcx, rbx
0x18000f09b  call    GetHandleFlags
0x18000f0a0  test    al, 10h
0x18000f0a2  jz      short loc_18000F0EB
0x18000f0a4  mov     rcx, rbx
0x18000f0a7  call    GetWimLastEOF
0x18000f0ac  mov     rdx, rax
0x18000f0af  mov     rcx, rbx
0x18000f0b2  call    SetWriteOffset
0x18000f0b7  mov     r8, qword ptr cs:g_liZero
0x18000f0be  mov     rcx, rbx
0x18000f0c1  xor     edx, edx
0x18000f0c3  call    GetWriteOffset
0x18000f0c8  mov     rcx, rbx
0x18000f0cb  mov     rdx, rax
0x18000f0ce  call    GetWimFileHandle
0x18000f0d3  mov     rcx, rax; hFile
0x18000f0d6  call    WIMSetFilePointerEx
0x18000f0db  mov     rcx, rbx
0x18000f0de  call    GetWimFileHandle
0x18000f0e3  mov     rcx, rax; hFile
0x18000f0e6  call    WIMSetEndOfFile
0x18000f0eb  test    r14d, r14d
0x18000f0ee  jz      short loc_18000F0FF
0x18000f0f0  mov     ecx, r14d; dwErrCode
0x18000f0f3  call    cs:__imp_SetLastError
0x18000f0fa  nop     dword ptr [rax+rax+00h]
0x18000f0ff  mov     eax, ebp
0x18000f101  jmp     short loc_18000F106
0x18000f103  mov     eax, r12d
0x18000f106  mov     rbx, [rsp+68h+arg_10]
0x18000f10e  add     rsp, 40h
0x18000f112  pop     r14
0x18000f114  pop     r13
0x18000f116  pop     r12
0x18000f118  pop     rdi
0x18000f119  pop     rbp
0x18000f11a  retn
```
