# CSpp::_ReadSnapshotOnDiskPropFromFile(ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x18001d47c`
- end: `0x18001d5f3`
- name: `?_ReadSnapshotOnDiskPropFromFile@CSpp@@AEAAJPEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct _SPP_ONDISK_SNAPSHOT_PROP *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18001d33c`
- `0x18001d5fc`

## callees

- `0x180008ed0`
- `0x18001d47c`
- `0x180020908`
- `0x1800220d8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180035b9a`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001d550`
- `KERNEL32!CreateFileW` at `0x18001d550`
- `KERNEL32!CloseHandle` at `0x18001d5d3`
- `KERNEL32!CloseHandle` at `0x18001d5d3`

## string_xrefs

- `0x18001d4cd`: `CSpp::_ReadSnapshotOnDiskPropFromFile`

## pseudocode

```c
__int64 __fastcall CSpp::_ReadSnapshotOnDiskPropFromFile(
        CSpp *this,
        const unsigned __int16 *a2,
        struct _SPP_ONDISK_SNAPSHOT_PROP *a3)
{
  __int64 FileW; // rdi
  __int16 v6; // ax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int LastFailureAsHRESULT; // ebx
  __int64 v10; // r8
  __int16 v11; // ax
  int v13; // [rsp+40h] [rbp-9h] BYREF
  __int16 v14; // [rsp+44h] [rbp-5h]
  __int16 v15; // [rsp+46h] [rbp-3h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSpp::_ReadSnapshotOnDiskPropFromFile", 9243, 1);
  FileW = -1;
  v6 = 9247;
  if ( a2 )
  {
    v14 = 9247;
    v6 = 9248;
    if ( a3 )
    {
      v13 = 0;
      v14 = 9248;
      memset_0(a3, 0, 0x98u);
      FileW = (__int64)CreateFileW(a2, 1u, 1u, 0, 3u, 0, 0);
      if ( FileW == -1 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
        v13 = LastFailureAsHRESULT;
        v11 = 9259;
      }
      else
      {
        v13 = 0;
        v14 = 9259;
        Free_SPP_ONDISK_SNAPSHOT_PROP(a3);
        LastFailureAsHRESULT = DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(
                                 (HANDLE)FileW,
                                 (__int64)&SPP_ONDISK_SNAPSHOT_PROP_Decode,
                                 (__int64)&stru_18003C2F0,
                                 a3);
        v13 = LastFailureAsHRESULT;
        v11 = 9263;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v14 = 9263;
LABEL_12:
          if ( LastFailureAsHRESULT >= 0 )
            goto LABEL_14;
          goto LABEL_13;
        }
      }
      v15 = v11;
      goto LABEL_12;
    }
  }
  v13 = -2147024809;
  v15 = v6;
LABEL_13:
  Free_SPP_ONDISK_SNAPSHOT_PROP(a3);
  LastFailureAsHRESULT = v13;
LABEL_14:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
    LastFailureAsHRESULT = v13;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v8, v10);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001d47c  push    rbp
0x18001d47e  push    rbx
0x18001d47f  push    rsi
0x18001d480  push    rdi
0x18001d481  lea     rbp, [rsp-3Fh]
0x18001d486  sub     rsp, 88h
0x18001d48d  mov     rsi, r8
0x18001d490  mov     rbx, rdx
0x18001d493  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d49a  lea     rax, WPP_GLOBAL_Control
0x18001d4a1  cmp     rcx, rax
0x18001d4a4  jz      short loc_18001D4C7
0x18001d4a6  test    dword ptr [rcx+1Ch], 20000000h
0x18001d4ad  jz      short loc_18001D4C7
0x18001d4af  mov     rcx, [rcx+10h]
0x18001d4b3  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001d4ba  mov     edx, 96h
0x18001d4bf  mov     r9, rbx
0x18001d4c2  call    WPP_SF_S
0x18001d4c7  mov     r9d, 1; unsigned __int16
0x18001d4cd  lea     rdx, aCsppReadsnapsh_1; "CSpp::_ReadSnapshotOnDiskPropFromFile"
0x18001d4d4  mov     r8d, 241Bh; unsigned __int16
0x18001d4da  lea     rcx, [rbp+57h+var_60]; this
0x18001d4de  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d4e3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d4e7  mov     eax, 241Fh
0x18001d4ec  test    rbx, rbx
0x18001d4ef  jnz     short loc_18001D501
0x18001d4f1  mov     [rbp+57h+var_60], 80070057h
0x18001d4f8  mov     [rbp+57h+var_5A], ax
0x18001d4fc  jmp     loc_18001D5BB
0x18001d501  mov     [rbp+57h+var_5C], ax
0x18001d505  mov     eax, 2420h
0x18001d50a  test    rsi, rsi
0x18001d50d  jz      short loc_18001D4F1
0x18001d50f  xor     edx, edx; Val
0x18001d511  mov     [rbp+57h+var_60], 0
0x18001d518  mov     r8d, 98h; Size
0x18001d51e  mov     [rbp+57h+var_5C], ax
0x18001d522  mov     rcx, rsi; void *
0x18001d525  call    memset_0
0x18001d52a  xor     r9d, r9d; lpSecurityAttributes
0x18001d52d  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18001d536  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001d53e  mov     rcx, rbx; lpFileName
0x18001d541  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001d549  lea     edx, [r9+1]; dwDesiredAccess
0x18001d54d  mov     r8d, edx; dwShareMode
0x18001d550  call    cs:__imp_CreateFileW
0x18001d556  mov     rdi, rax
0x18001d559  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d55d  jnz     short loc_18001D574
0x18001d55f  call    GetLastFailureAsHRESULT
0x18001d564  mov     ebx, eax
0x18001d566  mov     [rbp+57h+var_60], eax
0x18001d569  mov     eax, 242Bh
0x18001d56e  mov     [rbp+57h+var_5A], ax
0x18001d572  jmp     short loc_18001D5B7
0x18001d574  mov     eax, 242Bh
0x18001d579  mov     [rbp+57h+var_60], 0
0x18001d580  mov     rcx, rsi; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x18001d583  mov     [rbp+57h+var_5C], ax
0x18001d587  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x18001d58c  mov     r9, rsi
0x18001d58f  lea     r8, stru_18003C2F0
0x18001d596  lea     rdx, SPP_ONDISK_SNAPSHOT_PROP_Decode
0x18001d59d  mov     rcx, rdi; hFile
0x18001d5a0  call    ??$DeserializeFromFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x18001d5a5  mov     ebx, eax
0x18001d5a7  mov     [rbp+57h+var_60], eax
0x18001d5aa  test    eax, eax
0x18001d5ac  mov     eax, 242Fh
0x18001d5b1  js      short loc_18001D56E
0x18001d5b3  mov     [rbp+57h+var_5C], ax
0x18001d5b7  test    ebx, ebx
0x18001d5b9  jns     short loc_18001D5C6
0x18001d5bb  mov     rcx, rsi; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x18001d5be  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x18001d5c3  mov     ebx, [rbp+57h+var_60]
0x18001d5c6  lea     rax, [rdi-1]
0x18001d5ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d5ce  ja      short loc_18001D5DC
0x18001d5d0  mov     rcx, rdi; hObject
0x18001d5d3  call    cs:__imp_CloseHandle
0x18001d5d9  mov     ebx, [rbp+57h+var_60]
0x18001d5dc  lea     rcx, [rbp+57h+var_60]; this
0x18001d5e0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d5e5  mov     eax, ebx
0x18001d5e7  add     rsp, 88h
0x18001d5ee  pop     rdi
0x18001d5ef  pop     rsi
0x18001d5f0  pop     rbx
0x18001d5f1  pop     rbp
0x18001d5f2  retn
```
