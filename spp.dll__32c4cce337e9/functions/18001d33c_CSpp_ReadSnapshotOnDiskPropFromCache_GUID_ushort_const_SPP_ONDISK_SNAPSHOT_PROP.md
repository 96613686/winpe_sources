# CSpp::_ReadSnapshotOnDiskPropFromCache(_GUID,ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x18001d33c`
- end: `0x18001d473`
- name: `?_ReadSnapshotOnDiskPropFromCache@CSpp@@AEAAJU_GUID@@PEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(CSpp *this, struct _GUID *, const unsigned __int16 *, struct _SPP_ONDISK_SNAPSHOT_PROP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d0f0`

## callees

- `0x18001a4f0`
- `0x18001d33c`
- `0x18001d47c`
- `0x18002122c`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b76`
- `0x180035b9a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d451`

## string_xrefs

- `0x18001d38e`: `CSpp::_ReadSnapshotOnDiskPropFromCache`

## pseudocode

```c
__int64 __fastcall CSpp::_ReadSnapshotOnDiskPropFromCache(
        CSpp *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        struct _SPP_ONDISK_SNAPSHOT_PROP *a4)
{
  unsigned __int16 *v7; // rbx
  bool v8; // zf
  __int16 v9; // ax
  CSpp *v10; // rcx
  int SnapshotOnDiskPropCacheFilePath; // eax
  CSpp *v12; // rcx
  bool v13; // sf
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int16 *v18; // [rsp+30h] [rbp-50h] BYREF
  int SnapshotOnDiskPropFromFile; // [rsp+38h] [rbp-48h] BYREF
  __int16 v20; // [rsp+3Ch] [rbp-44h]
  __int16 v21; // [rsp+3Eh] [rbp-42h]
  struct _GUID v22; // [rsp+70h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, (_DWORD)a3, (_DWORD)a2, (__int64)a3);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&SnapshotOnDiskPropFromFile,
    "CSpp::_ReadSnapshotOnDiskPropFromCache",
    9289,
    1);
  v7 = 0;
  v18 = 0;
  v8 = memcmp_0(a2, &GUID_NULL, 0x10u) == 0;
  v9 = 9293;
  if ( !v8 && (v20 = 9293, v9 = 9294, a3) && (v20 = 9294, v9 = 9295, a4) )
  {
    SnapshotOnDiskPropFromFile = 0;
    v20 = 9295;
    memset_0(a4, 0, 0x98u);
    v22 = *a2;
    SnapshotOnDiskPropCacheFilePath = CSpp::_GetSnapshotOnDiskPropCacheFilePath(v10, &v22, a3, &v18);
    v7 = v18;
    v13 = SnapshotOnDiskPropCacheFilePath < 0;
    SnapshotOnDiskPropFromFile = SnapshotOnDiskPropCacheFilePath;
    v9 = 9299;
    if ( !v13 )
    {
      v20 = 9299;
      SnapshotOnDiskPropFromFile = CSpp::_ReadSnapshotOnDiskPropFromFile(v12, v18, a4);
      v9 = 9301;
      if ( SnapshotOnDiskPropFromFile >= 0 )
      {
        v20 = 9301;
        goto LABEL_12;
      }
    }
  }
  else
  {
    SnapshotOnDiskPropFromFile = -2147024809;
  }
  v21 = v9;
LABEL_12:
  CoTaskMemFree(v7);
  v14 = SnapshotOnDiskPropFromFile;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SnapshotOnDiskPropFromFile, v15, v16);
  return v14;
}

```

## disassembly

```asm
0x18001d33c  push    rbp
0x18001d33e  push    rbx
0x18001d33f  push    rsi
0x18001d340  push    rdi
0x18001d341  push    r14
0x18001d343  mov     rbp, rsp
0x18001d346  sub     rsp, 80h
0x18001d34d  mov     rsi, r9
0x18001d350  mov     rdi, r8
0x18001d353  mov     r14, rdx
0x18001d356  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d35d  lea     rax, WPP_GLOBAL_Control
0x18001d364  cmp     rcx, rax
0x18001d367  jz      short loc_18001D388
0x18001d369  test    dword ptr [rcx+1Ch], 20000000h
0x18001d370  jz      short loc_18001D388
0x18001d372  mov     rcx, [rcx+10h]
0x18001d376  mov     edx, 97h
0x18001d37b  mov     r9, r14
0x18001d37e  mov     [rsp+80h+var_60], r8
0x18001d383  call    WPP_SF__guid_S
0x18001d388  mov     r9d, 1; unsigned __int16
0x18001d38e  lea     rdx, aCsppReadsnapsh_2; "CSpp::_ReadSnapshotOnDiskPropFromCache"
0x18001d395  mov     r8d, 2449h; unsigned __int16
0x18001d39b  lea     rcx, [rbp+var_48]; this
0x18001d39f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d3a4  xor     ebx, ebx
0x18001d3a6  lea     rdx, GUID_NULL; Buf2
0x18001d3ad  mov     rcx, r14; Buf1
0x18001d3b0  mov     [rbp+var_50], rbx
0x18001d3b4  lea     r8d, [rbx+10h]; Size
0x18001d3b8  call    memcmp_0
0x18001d3bd  test    eax, eax
0x18001d3bf  mov     eax, 244Dh
0x18001d3c4  jnz     short loc_18001D3D3
0x18001d3c6  mov     [rbp+var_48], 80070057h
0x18001d3cd  mov     [rbp+var_42], ax
0x18001d3d1  jmp     short loc_18001D44E
0x18001d3d3  mov     [rbp+var_44], ax
0x18001d3d7  mov     eax, 244Eh
0x18001d3dc  test    rdi, rdi
0x18001d3df  jz      short loc_18001D3C6
0x18001d3e1  mov     [rbp+var_44], ax
0x18001d3e5  mov     eax, 244Fh
0x18001d3ea  test    rsi, rsi
0x18001d3ed  jz      short loc_18001D3C6
0x18001d3ef  xor     edx, edx; Val
0x18001d3f1  mov     [rbp+var_48], ebx
0x18001d3f4  mov     r8d, 98h; Size
0x18001d3fa  mov     [rbp+var_44], ax
0x18001d3fe  mov     rcx, rsi; void *
0x18001d401  call    memset_0
0x18001d406  movaps  xmm0, xmmword ptr [r14]
0x18001d40a  lea     r9, [rbp+var_50]; unsigned __int16 **
0x18001d40e  mov     r8, rdi; unsigned __int16 *
0x18001d411  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001d416  lea     rdx, [rbp+var_10]; struct _GUID
0x18001d41a  call    ?_GetSnapshotOnDiskPropCacheFilePath@CSpp@@AEAAJU_GUID@@PEBGPEAPEAG@Z; CSpp::_GetSnapshotOnDiskPropCacheFilePath(_GUID,ushort const *,ushort * *)
0x18001d41f  mov     rbx, [rbp+var_50]
0x18001d423  test    eax, eax
0x18001d425  mov     [rbp+var_48], eax
0x18001d428  mov     eax, 2453h
0x18001d42d  js      short loc_18001D3CD
0x18001d42f  mov     r8, rsi; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x18001d432  mov     [rbp+var_44], ax
0x18001d436  mov     rdx, rbx; unsigned __int16 *
0x18001d439  call    ?_ReadSnapshotOnDiskPropFromFile@CSpp@@AEAAJPEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_ReadSnapshotOnDiskPropFromFile(ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x18001d43e  mov     [rbp+var_48], eax
0x18001d441  test    eax, eax
0x18001d443  mov     eax, 2455h
0x18001d448  js      short loc_18001D3CD
0x18001d44a  mov     [rbp+var_44], ax
0x18001d44e  mov     rcx, rbx; pv
0x18001d451  call    cs:__imp_CoTaskMemFree
0x18001d457  mov     ebx, [rbp+var_48]
0x18001d45a  lea     rcx, [rbp+var_48]; this
0x18001d45e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d463  mov     eax, ebx
0x18001d465  add     rsp, 80h
0x18001d46c  pop     r14
0x18001d46e  pop     rdi
0x18001d46f  pop     rsi
0x18001d470  pop     rbx
0x18001d471  pop     rbp
0x18001d472  retn
```
