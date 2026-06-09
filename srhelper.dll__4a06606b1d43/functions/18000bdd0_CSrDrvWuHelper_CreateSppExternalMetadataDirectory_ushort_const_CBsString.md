# CSrDrvWuHelper::_CreateSppExternalMetadataDirectory(ushort const *,CBsString *)

- ea: `0x18000bdd0`
- end: `0x18000bf6a`
- name: `?_CreateSppExternalMetadataDirectory@CSrDrvWuHelper@@CAJPEBGPEAVCBsString@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *this, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000bbe0`

## callees

- `0x180003ce0`
- `0x18000bdd0`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e3b8`
- `0x18000e554`
- `0x180014f38`
- `0x180015590`
- `0x180015760`

## string_xrefs

- `0x18000be1e`: `CSrDrvWuHelper::_CreateSppExternalMetadataDirectory`
- `0x18000bead`: `System Volume Information\SPP\SppGroupCache`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_CreateSppExternalMetadataDirectory(
        const unsigned __int16 *a1,
        struct CBsString *this,
        __int64 a3,
        unsigned __int16 a4)
{
  __int16 v6; // ax
  int DirectoryUnderSVI; // ebx
  bool v8; // zf
  _WORD *v9; // rcx
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // r8
  struct _SECURITY_ATTRIBUTES *v13; // rdx
  _WORD *v14; // rcx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *v17; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-29h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-19h] BYREF
  __int64 v24; // [rsp+68h] [rbp-11h]
  int v25; // [rsp+70h] [rbp-9h] BYREF
  __int16 v26; // [rsp+74h] [rbp-5h]
  __int16 v27; // [rsp+76h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v25,
    "CSrDrvWuHelper::_CreateSppExternalMetadataDirectory",
    0x1A7u,
    a4);
  v24 = 0;
  lpFileName = (LPCWSTR)qword_18001A620;
  v6 = 426;
  if ( !this )
  {
    DirectoryUnderSVI = -2147024809;
    v25 = -2147024809;
    goto LABEL_6;
  }
  v8 = *((_DWORD *)this + 2) == 0;
  v25 = 0;
  v26 = 426;
  if ( !v8 )
  {
    v9 = *(_WORD **)this;
    *((_DWORD *)this + 2) = 0;
    *v9 = 0;
  }
  DirectoryUnderSVI = CBsString::Append((CBsString *)&lpFileName, a1);
  v25 = DirectoryUnderSVI;
  v6 = 430;
  if ( DirectoryUnderSVI < 0 )
    goto LABEL_6;
  v26 = 430;
  if ( !(_DWORD)v24 )
  {
    DirectoryUnderSVI = -2147020579;
    v25 = -2147020579;
LABEL_13:
    v6 = 431;
    goto LABEL_6;
  }
  v25 = CBsString::_CombinePathImpl(
          (CBsString *)&lpFileName,
          L"System Volume Information\\SPP\\SppGroupCache",
          0,
          v10,
          v16,
          v17,
          v18,
          v19,
          v20,
          v21,
          v22);
  DirectoryUnderSVI = v25;
  if ( v25 < 0 )
    goto LABEL_13;
  v26 = 431;
  DirectoryUnderSVI = SxCreateDirectoryUnderSVI(a1, v11, v12);
  v25 = DirectoryUnderSVI;
  v6 = 434;
  if ( DirectoryUnderSVI >= 0 )
  {
    v26 = 434;
    DirectoryUnderSVI = SxCreateDirectory(lpFileName, v13);
    v25 = DirectoryUnderSVI;
    v6 = 437;
    if ( DirectoryUnderSVI >= 0 )
    {
      v8 = *((_DWORD *)this + 2) == 0;
      v26 = 437;
      if ( !v8 )
      {
        v14 = *(_WORD **)this;
        *((_DWORD *)this + 2) = 0;
        *v14 = 0;
      }
      DirectoryUnderSVI = CBsString::Append(this, lpFileName);
      v25 = DirectoryUnderSVI;
      v6 = 439;
      if ( DirectoryUnderSVI >= 0 )
      {
        v26 = 439;
        goto LABEL_20;
      }
    }
  }
LABEL_6:
  v27 = v6;
LABEL_20:
  CBsString::_Release((CBsString *)&lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v25);
  return (unsigned int)DirectoryUnderSVI;
}

```

## disassembly

```asm
0x18000bdd0  push    rbp
0x18000bdd2  push    rbx
0x18000bdd3  push    rsi
0x18000bdd4  push    rdi
0x18000bdd5  lea     rbp, [rsp-3Fh]
0x18000bdda  sub     rsp, 0B8h
0x18000bde1  mov     rdi, rdx
0x18000bde4  mov     rsi, rcx
0x18000bde7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdee  lea     rax, WPP_GLOBAL_Control
0x18000bdf5  cmp     rcx, rax
0x18000bdf8  jz      short loc_18000BE18
0x18000bdfa  test    dword ptr [rcx+1Ch], 20000000h
0x18000be01  jz      short loc_18000BE18
0x18000be03  mov     rcx, [rcx+10h]
0x18000be07  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000be0e  mov     edx, 14h
0x18000be13  call    WPP_SF_
0x18000be18  mov     r8d, 1A7h; unsigned __int16
0x18000be1e  lea     rdx, aCsrdrvwuhelper_2; "CSrDrvWuHelper::_CreateSppExternalMetad"...
0x18000be25  lea     rcx, [rbp+57h+var_60]; this
0x18000be29  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000be2e  mov     [rbp+57h+var_68], 0
0x18000be36  lea     rax, qword_18001A620
0x18000be3d  mov     [rbp+57h+lpFileName], rax
0x18000be41  mov     eax, 1AAh
0x18000be46  test    rdi, rdi
0x18000be49  jnz     short loc_18000BE5C
0x18000be4b  mov     ebx, 80070057h
0x18000be50  mov     [rbp+57h+var_60], ebx
0x18000be53  mov     [rbp+57h+var_5A], ax
0x18000be57  jmp     loc_18000BF4A
0x18000be5c  cmp     dword ptr [rdi+8], 0
0x18000be60  mov     [rbp+57h+var_60], 0
0x18000be67  mov     [rbp+57h+var_5C], ax
0x18000be6b  jz      short loc_18000BE7C
0x18000be6d  mov     rcx, [rdi]
0x18000be70  xor     eax, eax
0x18000be72  mov     dword ptr [rdi+8], 0
0x18000be79  mov     [rcx], ax
0x18000be7c  mov     rdx, rsi; unsigned __int16 *
0x18000be7f  lea     rcx, [rbp+57h+lpFileName]; this
0x18000be83  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000be88  mov     ebx, eax
0x18000be8a  mov     [rbp+57h+var_60], eax
0x18000be8d  test    eax, eax
0x18000be8f  mov     eax, 1AEh
0x18000be94  js      short loc_18000BE53
0x18000be96  cmp     dword ptr [rbp+57h+var_68], 0
0x18000be9a  mov     [rbp+57h+var_5C], ax
0x18000be9e  jnz     short loc_18000BEAA
0x18000bea0  mov     ebx, 800710DDh
0x18000bea5  mov     [rbp+57h+var_60], ebx
0x18000bea8  jmp     short loc_18000BEC6
0x18000beaa  xor     r8d, r8d; unsigned __int16 *
0x18000bead  lea     rdx, aSystemVolumeIn_0; "System Volume Information\\SPP\\SppGrou"...
0x18000beb4  lea     rcx, [rbp+57h+lpFileName]; this
0x18000beb8  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000bebd  mov     [rbp+57h+var_60], eax
0x18000bec0  mov     ebx, eax
0x18000bec2  test    eax, eax
0x18000bec4  jns     short loc_18000BECD
0x18000bec6  mov     eax, 1AFh
0x18000becb  jmp     short loc_18000BE53
0x18000becd  mov     eax, 1AFh
0x18000bed2  mov     rcx, rsi; unsigned __int16 *
0x18000bed5  mov     [rbp+57h+var_5C], ax
0x18000bed9  call    ?SxCreateDirectoryUnderSVI@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectoryUnderSVI(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)
0x18000bede  mov     ebx, eax
0x18000bee0  mov     [rbp+57h+var_60], eax
0x18000bee3  test    eax, eax
0x18000bee5  mov     eax, 1B2h
0x18000beea  js      loc_18000BE53
0x18000bef0  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18000bef4  mov     [rbp+57h+var_5C], ax
0x18000bef8  call    ?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000befd  mov     ebx, eax
0x18000beff  mov     [rbp+57h+var_60], eax
0x18000bf02  test    eax, eax
0x18000bf04  mov     eax, 1B5h
0x18000bf09  js      loc_18000BE53
0x18000bf0f  cmp     dword ptr [rdi+8], 0
0x18000bf13  mov     [rbp+57h+var_5C], ax
0x18000bf17  jz      short loc_18000BF28
0x18000bf19  mov     rcx, [rdi]
0x18000bf1c  xor     eax, eax
0x18000bf1e  mov     dword ptr [rdi+8], 0
0x18000bf25  mov     [rcx], ax
0x18000bf28  mov     rdx, [rbp+57h+lpFileName]; unsigned __int16 *
0x18000bf2c  mov     rcx, rdi; this
0x18000bf2f  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000bf34  mov     ebx, eax
0x18000bf36  mov     [rbp+57h+var_60], eax
0x18000bf39  test    eax, eax
0x18000bf3b  mov     eax, 1B7h
0x18000bf40  js      loc_18000BE53
0x18000bf46  mov     [rbp+57h+var_5C], ax
0x18000bf4a  lea     rcx, [rbp+57h+lpFileName]; this
0x18000bf4e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bf53  lea     rcx, [rbp+57h+var_60]; this
0x18000bf57  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000bf5c  mov     eax, ebx
0x18000bf5e  add     rsp, 0B8h
0x18000bf65  pop     rdi
0x18000bf66  pop     rsi
0x18000bf67  pop     rbx
0x18000bf68  pop     rbp
0x18000bf69  retn
```
