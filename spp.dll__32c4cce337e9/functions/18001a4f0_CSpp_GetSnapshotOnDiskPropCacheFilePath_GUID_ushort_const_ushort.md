# CSpp::_GetSnapshotOnDiskPropCacheFilePath(_GUID,ushort const *,ushort * *)

- ea: `0x18001a4f0`
- end: `0x18001a65c`
- name: `?_GetSnapshotOnDiskPropCacheFilePath@CSpp@@AEAAJU_GUID@@PEBGPEAPEAG@Z`
- size: `364`
- prototype: `__int64 __fastcall(CSpp *this, struct _GUID *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d33c`
- `0x18001ff4c`

## callees

- `0x18001a37c`
- `0x18001a4f0`
- `0x18002122c`
- `0x1800268b4`
- `0x1800269ac`
- `0x180034f10`
- `0x180035390`
- `0x180035b00`
- `0x180035b76`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a631`

## string_xrefs

- `0x18001a544`: `CSpp::_GetSnapshotOnDiskPropCacheFilePath`
- `0x18001a5eb`: `OnlineMetadataCache`

## pseudocode

```c
__int64 __fastcall CSpp::_GetSnapshotOnDiskPropCacheFilePath(
        CSpp *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v7; // rbx
  bool v8; // zf
  CSpp *v9; // rcx
  __int16 v10; // ax
  int SnapshotOnDiskPropCacheFileName; // eax
  bool v12; // sf
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  const unsigned __int16 *v17; // [rsp+28h] [rbp-61h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-59h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-51h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-49h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-41h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-39h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-29h] BYREF
  int v24; // [rsp+68h] [rbp-21h] BYREF
  __int16 v25; // [rsp+6Ch] [rbp-1Dh]
  __int16 v26; // [rsp+6Eh] [rbp-1Bh]
  _QWORD v27[2]; // [rsp+A0h] [rbp+17h] BYREF
  struct _GUID v28; // [rsp+B0h] [rbp+27h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, (_DWORD)a3, (_DWORD)a2, (__int64)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "CSpp::_GetSnapshotOnDiskPropCacheFilePath", 8989, 1);
  v7 = 0;
  v27[1] = 0;
  v23 = 0;
  v27[0] = &FileName;
  v8 = memcmp_0(a2, &GUID_NULL, 0x10u) == 0;
  v10 = 8994;
  if ( !v8 && (v25 = 8994, v10 = 8995, a3) && (v25 = 8995, v10 = 8996, a4) )
  {
    v28 = *a2;
    v24 = 0;
    v25 = 8996;
    *a4 = 0;
    SnapshotOnDiskPropCacheFileName = CSpp::_GetSnapshotOnDiskPropCacheFileName(v9, &v28, &v23);
    v7 = v23;
    v12 = SnapshotOnDiskPropCacheFileName < 0;
    v24 = SnapshotOnDiskPropCacheFileName;
    v10 = 9000;
    if ( !v12 )
    {
      v25 = 9000;
      v24 = CBsString::SetPath(
              (CBsString *)v27,
              a3,
              L"System Volume Information\\SPP",
              L"OnlineMetadataCache",
              v23,
              v17,
              v18,
              v19,
              v20,
              v21,
              v22);
      v10 = 9002;
      if ( v24 >= 0 )
      {
        v25 = 9002;
        CBsString::Detach((CBsString *)v27, a4);
        goto LABEL_12;
      }
    }
  }
  else
  {
    v24 = -2147024809;
  }
  v26 = v10;
LABEL_12:
  CoTaskMemFree(v7);
  v13 = v24;
  CBsString::_Release((CBsString *)v27);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24, v14, v15);
  return v13;
}

```

## disassembly

```asm
0x18001a4f0  push    rbp
0x18001a4f2  push    rbx
0x18001a4f3  push    rsi
0x18001a4f4  push    rdi
0x18001a4f5  push    r14
0x18001a4f7  lea     rbp, [rsp-37h]
0x18001a4fc  sub     rsp, 0C0h
0x18001a503  mov     rdi, r9
0x18001a506  mov     rsi, r8
0x18001a509  mov     r14, rdx
0x18001a50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a513  lea     rax, WPP_GLOBAL_Control
0x18001a51a  cmp     rcx, rax
0x18001a51d  jz      short loc_18001A53E
0x18001a51f  test    dword ptr [rcx+1Ch], 20000000h
0x18001a526  jz      short loc_18001A53E
0x18001a528  mov     rcx, [rcx+10h]
0x18001a52c  mov     edx, 8Eh
0x18001a531  mov     r9, r14
0x18001a534  mov     [rsp+0E0h+var_C0], r8
0x18001a539  call    WPP_SF__guid_S
0x18001a53e  mov     r9d, 1; unsigned __int16
0x18001a544  lea     rdx, aCsppGetsnapsho_0; "CSpp::_GetSnapshotOnDiskPropCacheFilePa"...
0x18001a54b  mov     r8d, 231Dh; unsigned __int16
0x18001a551  lea     rcx, [rbp+57h+var_78]; this
0x18001a555  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a55a  xor     ebx, ebx
0x18001a55c  mov     [rbp+57h+var_38], 0
0x18001a564  lea     rax, FileName
0x18001a56b  mov     [rbp+57h+var_80], rbx
0x18001a56f  lea     rdx, GUID_NULL; Buf2
0x18001a576  mov     [rbp+57h+var_40], rax
0x18001a57a  mov     rcx, r14; Buf1
0x18001a57d  lea     r8d, [rbx+10h]; Size
0x18001a581  call    memcmp_0
0x18001a586  test    eax, eax
0x18001a588  mov     eax, 2322h
0x18001a58d  jnz     short loc_18001A59F
0x18001a58f  mov     [rbp+57h+var_78], 80070057h
0x18001a596  mov     [rbp+57h+var_72], ax
0x18001a59a  jmp     loc_18001A62E
0x18001a59f  mov     [rbp+57h+var_74], ax
0x18001a5a3  mov     eax, 2323h
0x18001a5a8  test    rsi, rsi
0x18001a5ab  jz      short loc_18001A58F
0x18001a5ad  mov     [rbp+57h+var_74], ax
0x18001a5b1  mov     eax, 2324h
0x18001a5b6  test    rdi, rdi
0x18001a5b9  jz      short loc_18001A58F
0x18001a5bb  movaps  xmm0, xmmword ptr [r14]
0x18001a5bf  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x18001a5c3  lea     rdx, [rbp+57h+var_30]; struct _GUID
0x18001a5c7  movdqa  xmmword ptr [rbp+57h+var_30.Data1], xmm0
0x18001a5cc  mov     [rbp+57h+var_78], ebx
0x18001a5cf  mov     [rbp+57h+var_74], ax
0x18001a5d3  mov     [rdi], rbx
0x18001a5d6  call    ?_GetSnapshotOnDiskPropCacheFileName@CSpp@@AEAAJU_GUID@@PEAPEAG@Z; CSpp::_GetSnapshotOnDiskPropCacheFileName(_GUID,ushort * *)
0x18001a5db  mov     rbx, [rbp+57h+var_80]
0x18001a5df  test    eax, eax
0x18001a5e1  mov     [rbp+57h+var_78], eax
0x18001a5e4  mov     eax, 2328h
0x18001a5e9  js      short loc_18001A596
0x18001a5eb  lea     r9, aOnlinemetadata; "OnlineMetadataCache"
0x18001a5f2  mov     [rbp+57h+var_74], ax
0x18001a5f6  lea     r8, aSystemVolumeIn_0; "System Volume Information\\SPP"
0x18001a5fd  mov     [rsp+0E0h+var_C0], rbx; unsigned __int16 *
0x18001a602  mov     rdx, rsi; unsigned __int16 *
0x18001a605  lea     rcx, [rbp+57h+var_40]; this
0x18001a609  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001a60e  mov     [rbp+57h+var_78], eax
0x18001a611  test    eax, eax
0x18001a613  mov     eax, 232Ah
0x18001a618  js      loc_18001A596
0x18001a61e  mov     rdx, rdi; unsigned __int16 **
0x18001a621  mov     [rbp+57h+var_74], ax
0x18001a625  lea     rcx, [rbp+57h+var_40]; this
0x18001a629  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18001a62e  mov     rcx, rbx; pv
0x18001a631  call    cs:__imp_CoTaskMemFree
0x18001a637  mov     ebx, [rbp+57h+var_78]
0x18001a63a  lea     rcx, [rbp+57h+var_40]; this
0x18001a63e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001a643  lea     rcx, [rbp+57h+var_78]; this
0x18001a647  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a64c  mov     eax, ebx
0x18001a64e  add     rsp, 0C0h
0x18001a655  pop     r14
0x18001a657  pop     rdi
0x18001a658  pop     rsi
0x18001a659  pop     rbx
0x18001a65a  pop     rbp
0x18001a65b  retn
```
