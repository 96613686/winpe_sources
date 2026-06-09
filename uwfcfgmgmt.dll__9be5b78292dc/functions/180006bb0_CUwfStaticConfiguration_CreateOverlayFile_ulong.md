# CUwfStaticConfiguration::CreateOverlayFile(ulong)

- ea: `0x180006bb0`
- end: `0x180006c74`
- name: `?CreateOverlayFile@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `196`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c300`
- `0x1800169c4`

## callees

- `0x180006bb0`
- `0x180007ad0`
- `0x180009848`
- `0x18000a3ac`
- `0x180011900`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006c51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006c51`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180006c32`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180006c32`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::CreateOverlayFile(CUwfStaticConfiguration *this, int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdx
  int OverlayFileName; // ebx
  __int64 v6; // r9
  unsigned int v8; // [rsp+20h] [rbp-40h]
  unsigned int v9; // [rsp+28h] [rbp-38h]
  unsigned int v10; // [rsp+30h] [rbp-30h]
  union _LARGE_INTEGER v11; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hFile; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v13; // [rsp+98h] [rbp+38h] BYREF

  v2 = a2;
  hFile = 0;
  v13 = 0;
  v11.QuadPart = 0;
  OverlayFileName = CUwfStaticConfiguration::GetOverlayFileName(this, &v13);
  if ( OverlayFileName >= 0 )
  {
    v11.QuadPart = v2 << 20;
    OverlayFileName = _NtCreateFile(v13, v4, &v11, v6, v8, v9, v10, &hFile);
    if ( OverlayFileName >= 0 )
    {
      OverlayFileName = UpdateOverlayFileHeader(hFile);
      if ( OverlayFileName >= 0 )
      {
        OverlayFileName = SetOverlayFileSecurity(hFile);
        if ( OverlayFileName >= 0 )
          FlushFileBuffers(hFile);
      }
    }
  }
  if ( hFile )
    ((void (*)(void))CNtCalls::s_pfnNtClose)();
  operator delete[](v13);
  if ( OverlayFileName < 0 )
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = OverlayFileName;
  return (unsigned int)OverlayFileName;
}

```

## disassembly

```asm
0x180006bb0  mov     [rsp-18h+arg_0], rbx
0x180006bb5  push    rbp
0x180006bb6  push    rsi
0x180006bb7  push    rdi
0x180006bb8  mov     rbp, rsp
0x180006bbb  sub     rsp, 60h
0x180006bbf  movsxd  rsi, edx
0x180006bc2  mov     rdi, rcx
0x180006bc5  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x180006bc9  mov     [rbp+hFile], 0
0x180006bd1  mov     [rbp+arg_18], 0
0x180006bd9  mov     qword ptr [rbp+var_10], 0
0x180006be1  call    ?GetOverlayFileName@CUwfStaticConfiguration@@QEAAJPEAPEAG@Z; CUwfStaticConfiguration::GetOverlayFileName(ushort * *)
0x180006be6  mov     ebx, eax
0x180006be8  test    eax, eax
0x180006bea  js      short loc_180006C38
0x180006bec  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180006bf0  lea     rax, [rbp+hFile]
0x180006bf4  shl     rsi, 14h
0x180006bf8  lea     r8, [rbp+var_10]; union _LARGE_INTEGER *
0x180006bfc  mov     qword ptr [rbp+var_10], rsi
0x180006c00  mov     [rsp+60h+var_28], rax; void **
0x180006c05  call    ?_NtCreateFile@@YAJPEBGKPEAT_LARGE_INTEGER@@KKKKPEAPEAX_N@Z; _NtCreateFile(ushort const *,ulong,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void * *,bool)
0x180006c0a  mov     ebx, eax
0x180006c0c  test    eax, eax
0x180006c0e  js      short loc_180006C38
0x180006c10  mov     rcx, [rbp+hFile]; void *
0x180006c14  call    ?UpdateOverlayFileHeader@@YAJPEAX@Z; UpdateOverlayFileHeader(void *)
0x180006c19  mov     ebx, eax
0x180006c1b  test    eax, eax
0x180006c1d  js      short loc_180006C38
0x180006c1f  mov     rcx, [rbp+hFile]; Handle
0x180006c23  call    ?SetOverlayFileSecurity@@YAJPEAX@Z; SetOverlayFileSecurity(void *)
0x180006c28  mov     ebx, eax
0x180006c2a  test    eax, eax
0x180006c2c  js      short loc_180006C38
0x180006c2e  mov     rcx, [rbp+hFile]; hFile
0x180006c32  call    cs:__imp_FlushFileBuffers
0x180006c38  mov     rcx, [rbp+hFile]
0x180006c3c  test    rcx, rcx
0x180006c3f  jz      short loc_180006C4D
0x180006c41  mov     rax, cs:?s_pfnNtClose@CNtCalls@@0P6AJPEAX@ZEA; long (*CNtCalls::s_pfnNtClose)(void *)
0x180006c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4d  mov     rcx, [rbp+arg_18]
0x180006c51  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006c57  test    ebx, ebx
0x180006c59  jns     short loc_180006C62
0x180006c5b  mov     rax, [rdi+20h]
0x180006c5f  mov     [rax+10h], ebx
0x180006c62  mov     eax, ebx
0x180006c64  mov     rbx, [rsp+60h+arg_0]
0x180006c6c  add     rsp, 60h
0x180006c70  pop     rdi
0x180006c71  pop     rsi
0x180006c72  pop     rbp
0x180006c73  retn
```
