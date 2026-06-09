# WIMCreateFile

- ea: `0x18000db70`
- end: `0x18000e229`
- name: `WIMCreateFile`
- size: `1721`
- prototype: `void *__fastcall(unsigned __int16 *, __int64, __int64, int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c9c4`

## callees

- `0x18000d938`
- `0x18000db70`
- `0x18000e230`
- `0x180010be0`
- `0x180011880`
- `0x180011904`
- `0x1800119b4`
- `0x180011a38`
- `0x180011a84`
- `0x180011bb8`
- `0x18001219c`
- `0x180012208`
- `0x180012304`
- `0x180012744`
- `0x180012ccc`
- `0x180013308`
- `0x180013690`
- `0x180013a30`
- `0x1800147dc`
- `0x180016f8c`
- `0x180017344`
- `0x18001756c`
- `0x180017aa4`
- `0x18001822c`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000e19b`
- `KERNEL32!HeapFree` at `0x18000e19b`
- `KERNEL32!HeapAlloc` at `0x18000dc47`
- `KERNEL32!HeapAlloc` at `0x18000dc47`
- `KERNEL32!GetLastError` at `0x18000dbe5`
- `KERNEL32!GetLastError` at `0x18000de3b`
- `KERNEL32!GetLastError` at `0x18000dec4`
- `KERNEL32!GetLastError` at `0x18000deee`
- `KERNEL32!GetLastError` at `0x18000e1d0`
- `KERNEL32!GetLastError` at `0x18000e1e9`
- `KERNEL32!GetLastError` at `0x18000dbe5`
- `KERNEL32!GetLastError` at `0x18000de3b`
- `KERNEL32!GetLastError` at `0x18000dec4`
- `KERNEL32!GetLastError` at `0x18000deee`
- `KERNEL32!GetLastError` at `0x18000e1d0`
- `KERNEL32!GetLastError` at `0x18000e1e9`
- `KERNEL32!SetLastError` at `0x18000dbb7`
- `KERNEL32!SetLastError` at `0x18000e1a9`
- `KERNEL32!SetLastError` at `0x18000dbb7`
- `KERNEL32!SetLastError` at `0x18000e1a9`
- `KERNEL32!GetFileSizeEx` at `0x18000deae`
- `KERNEL32!GetFileSizeEx` at `0x18000deae`
- `KERNEL32!GetProcessHeap` at `0x18000dc2d`
- `KERNEL32!GetProcessHeap` at `0x18000e187`
- `KERNEL32!GetProcessHeap` at `0x18000dc2d`
- `KERNEL32!GetProcessHeap` at `0x18000e187`

## string_xrefs

- `0x18000df1d`: `WIMCreateFile`
- `0x18000df2b`: `Fail to read WIM header`

## pseudocode

```c
void *__fastcall WIMCreateFile(unsigned __int16 *a1, __int64 a2, __int64 a3, int a4, unsigned int a5, int *a6)
{
  void *v7; // rbx
  DWORD LastError; // edi
  int v9; // ebp
  WCHAR *v11; // rax
  WCHAR *v12; // r13
  HANDLE ProcessHeap; // rax
  void *v14; // rax
  unsigned int v15; // r14d
  int v16; // edx
  int v17; // edx
  int v18; // r11d
  int v19; // r10d
  _DWORD *v20; // rax
  int v21; // r8d
  int FlagsAndAttributes; // eax
  int v23; // r11d
  int v24; // r9d
  int v25; // edx
  int v26; // r10d
  _DWORD *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  LARGE_INTEGER *v33; // rcx
  void *WimFileHandle; // rax
  int v35; // eax
  int WimPath; // eax
  NTSTATUS Status; // edx
  __int64 WimHeader; // rax
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  _QWORD *v49; // rcx
  __int64 v50; // rax
  __int16 v51; // cx
  __int16 v52; // cx
  _QWORD *v53; // rax
  HANDLE v54; // rax
  _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-50h] BYREF
  int *v57; // [rsp+50h] [rbp-48h]

  v57 = a6;
  FileSize.QuadPart = 0;
  v7 = 0;
  LastError = 0;
  v9 = 0;
  SetLastError(0);
  if ( a6 )
    *a6 = 0;
  v11 = (WCHAR *)AllocFullPathEx(a1);
  v12 = v11;
  if ( v11 )
  {
    if ( (a4 & 0x1000) == 0 && (!*v11 || !FileSize.QuadPart || !*(_WORD *)FileSize.QuadPart) )
    {
      LastError = 87;
      goto LABEL_114;
    }
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 8u, 0x258u);
    v7 = v14;
    if ( !v14 )
    {
      LastError = 14;
      v7 = 0;
      goto LABEL_114;
    }
    memset_0(v14, 0, 0x258u);
    *(_DWORD *)v7 = -17960959;
    *((_DWORD *)v7 + 107) |= 0x80000000;
    *((_DWORD *)v7 + 109) = 3;
    if ( (a4 & 0xDFFFCFBD) != 0 )
    {
      LastError = 87;
      goto LABEL_122;
    }
    v15 = 2;
    if ( (a4 & 2) != 0 )
    {
      v16 = GetFlagsAndAttributes(v7) | 2;
      if ( v7 )
        *((_DWORD *)v7 + 110) = v16;
    }
    if ( (a4 & 0x40) != 0 )
    {
      v17 = GetFlagsAndAttributes(v7) | 0x40;
      if ( *(_DWORD *)v7 == v19 )
      {
        v20 = v7;
      }
      else
      {
        if ( *(_DWORD *)v7 != v18 )
          goto LABEL_26;
        v20 = (_DWORD *)*((_QWORD *)v7 + 1);
      }
      if ( v20 )
        v20[110] = v17;
    }
LABEL_26:
    v21 = a4 & 0x20000000;
    if ( (a4 & 0x20000000) == 0 )
      goto LABEL_33;
    FlagsAndAttributes = GetFlagsAndAttributes(v7);
    v25 = v24 | FlagsAndAttributes;
    if ( *(_DWORD *)v7 == v26 )
    {
      v27 = v7;
    }
    else
    {
      if ( *(_DWORD *)v7 != v23 )
        goto LABEL_33;
      v27 = (_DWORD *)*((_QWORD *)v7 + 1);
    }
    if ( v27 )
      v27[110] = v25;
LABEL_33:
    v28 = 4;
    if ( (a4 & 0x2000) == 0 )
      v28 = a5;
    if ( (unsigned int)v28 > 2 )
    {
      if ( (_DWORD)v28 == 3 )
      {
        if ( !v21 )
          goto LABEL_39;
      }
      else if ( (unsigned int)v28 <= 5 )
      {
        v28 = 7;
      }
      else if ( (_DWORD)v28 != 7 )
      {
LABEL_39:
        LastError = 87;
LABEL_120:
        v9 = 0;
        goto LABEL_121;
      }
    }
    SetCompressionType(v7, v28);
    if ( (a4 & 0x1000) != 0 )
      v29 = WimStrDupe(a1);
    else
      v29 = AllocFullPathEx(v12);
    v30 = v29;
    if ( *(_DWORD *)v7 == -17960958 )
    {
      v31 = (_QWORD *)*((_QWORD *)v7 + 1);
    }
    else
    {
      if ( *(_DWORD *)v7 != -17960959 )
        goto LABEL_52;
      v31 = v7;
    }
    if ( v31 )
      v31[66] = v30;
LABEL_52:
    if ( !GetWimPath(v7) )
      goto LABEL_119;
    if ( *(_DWORD *)v7 == -17960959 )
    {
      v32 = v7;
    }
    else
    {
      if ( *(_DWORD *)v7 != -17960958 )
        goto LABEL_59;
      v32 = (_QWORD *)*((_QWORD *)v7 + 1);
    }
    if ( v32 )
      v32[1] = -1;
LABEL_59:
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))CreateWimFile)(v7, (LARGE_INTEGER)g_liZero.QuadPart)
      && GetWimFileHandle(v7) != -1 )
    {
      *((_DWORD *)v7 + 109) = 3;
      v9 = 1;
      if ( !(unsigned int)WimInitXmlInfo(v7) )
      {
        LastError = GetLastError();
        goto LABEL_121;
      }
      *((_QWORD *)v7 + 58) = InitializeWimHashTable();
      if ( *(_DWORD *)v7 == -17960958 )
      {
        v33 = (LARGE_INTEGER *)*((_QWORD *)v7 + 1);
      }
      else
      {
        if ( *(_DWORD *)v7 != -17960959 )
          goto LABEL_69;
        v33 = (LARGE_INTEGER *)v7;
      }
      if ( v33 )
        v33[70] = g_liZero;
LABEL_69:
      FileSize.QuadPart = 0;
      SetHandleFlag(v7, 1);
      WimFileHandle = (void *)GetWimFileHandle(v7);
      if ( g_useFileIOCallbacks )
        v35 = WIMGetFileSizeEx(WimFileHandle, &FileSize);
      else
        v35 = GetFileSizeEx(WimFileHandle, &FileSize);
      if ( !v35 )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 13;
        goto LABEL_122;
      }
      if ( !(unsigned int)ReadWimHeader(v7, 0) )
      {
        LastError = GetLastError();
        WimPath = GetWimPath(v7);
        WIMLogMsg(1, 0, WimPath, (int)L"Fail to read WIM header", Status, (__int64)L"WIMCreateFile", 430);
        if ( LastError )
        {
LABEL_122:
          if ( v7 )
          {
            SetHandleFlag(v7, 1);
            WIMCloseHandle(v7);
            v7 = 0;
          }
          goto LABEL_114;
        }
      }
      if ( !(unsigned int)LoadIntegrityInfo(v7) || !(unsigned int)VerifyIntegrityInfo((_DWORD)v7) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1392;
        goto LABEL_122;
      }
      if ( *((int *)v7 + 107) < 0 && !(unsigned int)LoadOffsetTable(v7) || !(unsigned int)LoadXmlInformation(v7) )
      {
        LastError = 13;
        goto LABEL_122;
      }
      GetWimHeader(v7);
      WimHeader = GetWimHeader(v7);
      SetWriteOffset(v7, *(_QWORD *)(WimHeader + 64) + v39);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(v7, 0, (LARGE_INTEGER)g_liZero.QuadPart);
      v40 = GetWimHeader(v7);
      if ( *(_QWORD *)(v40 + 128) >= v41 && *(_QWORD *)(GetWimHeader(v7) + 136) )
      {
        GetWimHeader(v7);
        v42 = GetWimHeader(v7);
        SetWriteOffset(v7, *(_QWORD *)(v42 + 128) + v43);
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(v7, 0, (LARGE_INTEGER)g_liZero.QuadPart);
      v44 = GetWimHeader(v7);
      if ( *(_QWORD *)(v44 + 264) >= v45 && *(_QWORD *)(GetWimHeader(v7) + 272) )
      {
        GetWimHeader(v7);
        v46 = GetWimHeader(v7);
        SetWriteOffset(v7, *(_QWORD *)(v46 + 264) + v47);
      }
      v48 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(v7, 0, (LARGE_INTEGER)g_liZero.QuadPart);
      if ( *(_DWORD *)v7 == -17960958 )
      {
        v49 = (_QWORD *)*((_QWORD *)v7 + 1);
      }
      else
      {
        if ( *(_DWORD *)v7 != -17960959 )
          goto LABEL_96;
        v49 = v7;
      }
      if ( v49 )
        v49[70] = v48;
LABEL_96:
      if ( (GetHandleFlags(v7) & 0x100) != 0 )
      {
        v50 = GetWimHeader(v7);
        SetWriteOffset(v7, *(_QWORD *)(v50 + 64));
      }
      if ( (*(_DWORD *)(GetWimHeader(v7) + 16) & 0x40000) == 0 )
      {
        if ( (*(_DWORD *)(GetWimHeader(v7) + 16) & 0x20000) != 0 )
        {
          v15 = 1;
        }
        else if ( (*(_DWORD *)(GetWimHeader(v7) + 16) & 0x200000) != 0 )
        {
          v15 = 7;
        }
        else
        {
          v15 = (*(_DWORD *)(GetWimHeader(v7) + 16) & 0x80000) != 0 ? 3 : 0;
        }
      }
      SetCompressionType(v7, v15);
      v51 = *(_WORD *)(GetWimHeader(v7) + 40);
      if ( *(_DWORD *)v7 == -17960959 )
        *((_WORD *)v7 + 228) = v51;
      v52 = *(_WORD *)(GetWimHeader(v7) + 42);
      if ( *(_DWORD *)v7 == -17960959 )
      {
        *((_WORD *)v7 + 229) = v52;
        v53 = v7;
      }
      else
      {
        if ( *(_DWORD *)v7 != -17960958 )
          goto LABEL_112;
        v53 = (_QWORD *)*((_QWORD *)v7 + 1);
      }
      if ( v53 )
        v53[73] = v7;
      goto LABEL_112;
    }
LABEL_119:
    LastError = GetLastError();
    goto LABEL_120;
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 14;
LABEL_121:
  if ( LastError )
    goto LABEL_122;
LABEL_112:
  if ( v57 )
    *v57 = v9;
LABEL_114:
  LogSharingViolationErrorInfo(v12, LastError);
  if ( v12 )
  {
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v12);
  }
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18000db70  mov     [rsp+arg_8], rbx
0x18000db75  push    rbp
0x18000db76  push    rsi
0x18000db77  push    rdi
0x18000db78  push    r12
0x18000db7a  push    r13
0x18000db7c  push    r14
0x18000db7e  push    r15
0x18000db80  sub     rsp, 60h
0x18000db84  mov     r14, [rsp+98h+arg_28]
0x18000db8c  xor     r13d, r13d
0x18000db8f  mov     r12d, [rsp+98h+arg_20]
0x18000db97  mov     r15, rcx
0x18000db9a  xor     ecx, ecx; dwErrCode
0x18000db9c  mov     [rsp+98h+var_48], r14
0x18000dba1  mov     qword ptr [rsp+98h+FileSize], r13
0x18000dba6  mov     ebx, r13d
0x18000dba9  mov     edi, r13d
0x18000dbac  mov     [rsp+98h+var_58], r13d
0x18000dbb1  mov     ebp, r13d
0x18000dbb4  mov     esi, r9d
0x18000dbb7  call    cs:__imp_SetLastError
0x18000dbbe  nop     dword ptr [rax+rax+00h]
0x18000dbc3  test    r14, r14
0x18000dbc6  jz      short loc_18000DBCB
0x18000dbc8  mov     [r14], r13d
0x18000dbcb  lea     r8, [rsp+98h+FileSize]
0x18000dbd0  xor     edx, edx
0x18000dbd2  mov     rcx, r15; lpFileName
0x18000dbd5  call    AllocFullPathEx
0x18000dbda  xor     r14d, r14d
0x18000dbdd  mov     r13, rax
0x18000dbe0  test    rax, rax
0x18000dbe3  jnz     short loc_18000DC03
0x18000dbe5  call    cs:__imp_GetLastError
0x18000dbec  nop     dword ptr [rax+rax+00h]
0x18000dbf1  mov     edi, eax
0x18000dbf3  xor     esi, esi
0x18000dbf5  test    edi, edi
0x18000dbf7  lea     eax, [r13+0Eh]
0x18000dbfb  cmovz   edi, eax
0x18000dbfe  jmp     loc_18000E1FB
0x18000dc03  mov     ebp, esi
0x18000dc05  and     ebp, 1000h
0x18000dc0b  jnz     short loc_18000DC2D
0x18000dc0d  cmp     [rax], r14w
0x18000dc11  jz      short loc_18000DC23
0x18000dc13  mov     rax, qword ptr [rsp+98h+FileSize]
0x18000dc18  test    rax, rax
0x18000dc1b  jz      short loc_18000DC23
0x18000dc1d  cmp     [rax], r14w
0x18000dc21  jnz     short loc_18000DC2D
0x18000dc23  mov     edi, 57h ; 'W'
0x18000dc28  jmp     loc_18000E178
0x18000dc2d  call    cs:__imp_GetProcessHeap
0x18000dc34  nop     dword ptr [rax+rax+00h]
0x18000dc39  mov     edx, 8; dwFlags
0x18000dc3e  mov     r8d, 258h; dwBytes
0x18000dc44  mov     rcx, rax; hHeap
0x18000dc47  call    cs:__imp_HeapAlloc
0x18000dc4e  nop     dword ptr [rax+rax+00h]
0x18000dc53  mov     rbx, rax
0x18000dc56  test    rax, rax
0x18000dc59  jnz     short loc_18000DC67
0x18000dc5b  xor     esi, esi
0x18000dc5d  lea     edi, [rax+0Eh]
0x18000dc60  mov     ebx, esi
0x18000dc62  jmp     loc_18000E178
0x18000dc67  xor     edx, edx; Val
0x18000dc69  mov     r8d, 258h; Size
0x18000dc6f  mov     rcx, rbx; void *
0x18000dc72  call    memset_0
0x18000dc77  mov     r10d, 0FEEDF001h
0x18000dc7d  mov     [rbx], r10d
0x18000dc80  bts     dword ptr [rbx+1ACh], 1Fh
0x18000dc88  mov     dword ptr [rbx+1B4h], 3
0x18000dc92  test    esi, 0DFFFCFBDh
0x18000dc98  jz      short loc_18000DCA6
0x18000dc9a  mov     edi, 57h ; 'W'
0x18000dc9f  xor     esi, esi
0x18000dca1  jmp     loc_18000E203
0x18000dca6  mov     r14d, 2
0x18000dcac  mov     r11d, 0FEEDF002h
0x18000dcb2  test    r14b, sil
0x18000dcb5  jz      short loc_18000DCCF
0x18000dcb7  mov     rcx, rbx
0x18000dcba  call    GetFlagsAndAttributes
0x18000dcbf  mov     edx, eax
0x18000dcc1  or      edx, r14d
0x18000dcc4  test    rbx, rbx
0x18000dcc7  jz      short loc_18000DCCF
0x18000dcc9  mov     [rbx+1B8h], edx
0x18000dccf  test    sil, 40h
0x18000dcd3  jz      short loc_18000DD00
0x18000dcd5  mov     rcx, rbx
0x18000dcd8  call    GetFlagsAndAttributes
0x18000dcdd  mov     edx, eax
0x18000dcdf  or      edx, 40h
0x18000dce2  cmp     [rbx], r10d
0x18000dce5  jz      short loc_18000DCF2
0x18000dce7  cmp     [rbx], r11d
0x18000dcea  jnz     short loc_18000DD00
0x18000dcec  mov     rax, [rbx+8]
0x18000dcf0  jmp     short loc_18000DCF5
0x18000dcf2  mov     rax, rbx
0x18000dcf5  test    rax, rax
0x18000dcf8  jz      short loc_18000DD00
0x18000dcfa  mov     [rax+1B8h], edx
0x18000dd00  mov     r8d, esi
0x18000dd03  mov     r9d, 20000000h
0x18000dd09  and     r8d, r9d
0x18000dd0c  jz      short loc_18000DD39
0x18000dd0e  mov     rcx, rbx
0x18000dd11  call    GetFlagsAndAttributes
0x18000dd16  mov     edx, eax
0x18000dd18  or      edx, r9d
0x18000dd1b  cmp     [rbx], r10d
0x18000dd1e  jz      short loc_18000DD2B
0x18000dd20  cmp     [rbx], r11d
0x18000dd23  jnz     short loc_18000DD39
0x18000dd25  mov     rax, [rbx+8]
0x18000dd29  jmp     short loc_18000DD2E
0x18000dd2b  mov     rax, rbx
0x18000dd2e  test    rax, rax
0x18000dd31  jz      short loc_18000DD39
0x18000dd33  mov     [rax+1B8h], edx
0x18000dd39  bt      esi, 0Dh
0x18000dd3d  mov     edx, 4
0x18000dd42  cmovnb  edx, r12d
0x18000dd46  cmp     edx, r14d
0x18000dd49  jbe     short loc_18000DD6D
0x18000dd4b  cmp     edx, 3
0x18000dd4e  jz      short loc_18000DD85
0x18000dd50  jbe     short loc_18000DD5C
0x18000dd52  cmp     edx, 5
0x18000dd55  jbe     short loc_18000DD68
0x18000dd57  cmp     edx, 7
0x18000dd5a  jz      short loc_18000DD6D
0x18000dd5c  xor     esi, esi
0x18000dd5e  mov     edi, 57h ; 'W'
0x18000dd63  jmp     loc_18000E1F7
0x18000dd68  mov     edx, 7
0x18000dd6d  xor     esi, esi
0x18000dd6f  mov     rcx, rbx
0x18000dd72  call    SetCompressionType
0x18000dd77  test    ebp, ebp
0x18000dd79  jz      short loc_18000DD8E
0x18000dd7b  mov     rcx, r15; unsigned __int16 *
0x18000dd7e  call    WimStrDupe
0x18000dd83  jmp     short loc_18000DD9B
0x18000dd85  xor     esi, esi
0x18000dd87  test    r8d, r8d
0x18000dd8a  jz      short loc_18000DD5E
0x18000dd8c  jmp     short loc_18000DD6F
0x18000dd8e  xor     r8d, r8d
0x18000dd91  xor     edx, edx
0x18000dd93  mov     rcx, r13; lpFileName
0x18000dd96  call    AllocFullPathEx
0x18000dd9b  mov     r15d, 0FEEDF002h
0x18000dda1  mov     rcx, rax
0x18000dda4  mov     r12d, 0FEEDF001h
0x18000ddaa  cmp     [rbx], r15d
0x18000ddad  jnz     short loc_18000DDB5
0x18000ddaf  mov     rax, [rbx+8]
0x18000ddb3  jmp     short loc_18000DDBD
0x18000ddb5  cmp     [rbx], r12d
0x18000ddb8  jnz     short loc_18000DDC9
0x18000ddba  mov     rax, rbx
0x18000ddbd  test    rax, rax
0x18000ddc0  jz      short loc_18000DDC9
0x18000ddc2  mov     [rax+210h], rcx
0x18000ddc9  mov     rcx, rbx
0x18000ddcc  call    GetWimPath
0x18000ddd1  test    rax, rax
0x18000ddd4  jz      loc_18000E1E9
0x18000ddda  cmp     [rbx], r12d
0x18000dddd  jnz     short loc_18000DDE4
0x18000dddf  mov     rax, rbx
0x18000dde2  jmp     short loc_18000DDED
0x18000dde4  cmp     [rbx], r15d
0x18000dde7  jnz     short loc_18000DDF7
0x18000dde9  mov     rax, [rbx+8]
0x18000dded  test    rax, rax
0x18000ddf0  jz      short loc_18000DDF7
0x18000ddf2  or      qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18000ddf7  mov     rdx, qword ptr cs:g_liZero
0x18000ddfe  mov     rcx, rbx
0x18000de01  call    CreateWimFile
0x18000de06  test    eax, eax
0x18000de08  jz      loc_18000E1E9
0x18000de0e  mov     rcx, rbx
0x18000de11  call    GetWimFileHandle
0x18000de16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000de1a  jz      loc_18000E1E9
0x18000de20  mov     rcx, rbx
0x18000de23  mov     dword ptr [rbx+1B4h], 3
0x18000de2d  mov     ebp, 1
0x18000de32  call    WimInitXmlInfo
0x18000de37  test    eax, eax
0x18000de39  jnz     short loc_18000DE4E
0x18000de3b  call    cs:__imp_GetLastError
0x18000de42  nop     dword ptr [rax+rax+00h]
0x18000de47  mov     edi, eax
0x18000de49  jmp     loc_18000E1FB
0x18000de4e  call    InitializeWimHashTable
0x18000de53  mov     [rbx+1D0h], rax
0x18000de5a  mov     rax, qword ptr cs:g_liZero
0x18000de61  cmp     [rbx], r15d
0x18000de64  jnz     short loc_18000DE6C
0x18000de66  mov     rcx, [rbx+8]
0x18000de6a  jmp     short loc_18000DE74
0x18000de6c  cmp     [rbx], r12d
0x18000de6f  jnz     short loc_18000DE80
0x18000de71  mov     rcx, rbx
0x18000de74  test    rcx, rcx
0x18000de77  jz      short loc_18000DE80
0x18000de79  mov     [rcx+230h], rax
0x18000de80  mov     edx, ebp
0x18000de82  mov     qword ptr [rsp+98h+FileSize], rsi
0x18000de87  mov     rcx, rbx
0x18000de8a  call    SetHandleFlag
0x18000de8f  mov     rcx, rbx
0x18000de92  call    GetWimFileHandle
0x18000de97  cmp     cs:g_useFileIOCallbacks, esi
0x18000de9d  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x18000dea2  mov     rcx, rax; hFile
0x18000dea5  jz      short loc_18000DEAE
0x18000dea7  call    WIMGetFileSizeEx
0x18000deac  jmp     short loc_18000DEBA
0x18000deae  call    cs:__imp_GetFileSizeEx
0x18000deb5  nop     dword ptr [rax+rax+00h]
0x18000deba  mov     r15d, 0Dh
0x18000dec0  test    eax, eax
0x18000dec2  jnz     short loc_18000DEE0
0x18000dec4  call    cs:__imp_GetLastError
0x18000decb  nop     dword ptr [rax+rax+00h]
0x18000ded0  test    eax, eax
0x18000ded2  mov     edi, eax
0x18000ded4  cmovz   edi, r15d
0x18000ded8  test    edi, edi
0x18000deda  jnz     loc_18000E203
0x18000dee0  xor     edx, edx
0x18000dee2  mov     rcx, rbx
0x18000dee5  call    ReadWimHeader
0x18000deea  test    eax, eax
0x18000deec  jnz     short loc_18000DF45
0x18000deee  call    cs:__imp_GetLastError
0x18000def5  nop     dword ptr [rax+rax+00h]
0x18000defa  movzx   edx, ax
0x18000defd  mov     rcx, rbx
0x18000df00  or      edx, 80070000h
0x18000df06  mov     edi, eax
0x18000df08  test    eax, eax
0x18000df0a  cmovle  edx, eax
0x18000df0d  call    GetWimPath
0x18000df12  mov     r8, rax; int
0x18000df15  mov     [rsp+98h+var_68], 1AEh; int
0x18000df1d  lea     rax, aWimcreatefile; "WIMCreateFile"
0x18000df24  mov     ecx, ebp; int
0x18000df26  mov     [rsp+98h+var_70], rax; __int64
0x18000df2b  lea     r9, aFailToReadWimH; "Fail to read WIM header"
0x18000df32  mov     [rsp+98h+Status], edx; Status
0x18000df36  xor     edx, edx; int
0x18000df38  call    _WIMLogMsg
0x18000df3d  test    edi, edi
0x18000df3f  jnz     loc_18000E203
0x18000df45  mov     rcx, rbx
0x18000df48  call    LoadIntegrityInfo
0x18000df4d  test    eax, eax
0x18000df4f  jz      loc_18000E1D0
0x18000df55  mov     rcx, rbx
0x18000df58  call    VerifyIntegrityInfo
0x18000df5d  test    eax, eax
0x18000df5f  jz      loc_18000E1D0
0x18000df65  cmp     [rbx+1ACh], esi
0x18000df6b  jge     short loc_18000DF81
0x18000df6d  mov     rcx, rbx
0x18000df70  call    LoadOffsetTable
0x18000df75  test    eax, eax
0x18000df77  jnz     short loc_18000DF81
0x18000df79  mov     edi, r15d
0x18000df7c  jmp     loc_18000E203
0x18000df81  mov     rcx, rbx
0x18000df84  call    LoadXmlInformation
0x18000df89  test    eax, eax
0x18000df8b  jz      short loc_18000DF79
0x18000df8d  mov     rcx, rbx
0x18000df90  call    GetWimHeader
0x18000df95  mov     rcx, rbx
0x18000df98  mov     rdx, [rax+48h]
0x18000df9c  call    GetWimHeader
0x18000dfa1  mov     rcx, rbx
0x18000dfa4  add     rdx, [rax+40h]
0x18000dfa8  call    SetWriteOffset
0x18000dfad  mov     r8, qword ptr cs:g_liZero
0x18000dfb4  mov     rcx, rbx
0x18000dfb7  xor     edx, edx
0x18000dfb9  call    GetWriteOffset
0x18000dfbe  mov     rcx, rbx
0x18000dfc1  mov     r8, rax
  ... truncated ...
```
