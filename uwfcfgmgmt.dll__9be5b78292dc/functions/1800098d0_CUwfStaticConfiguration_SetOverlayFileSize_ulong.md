# CUwfStaticConfiguration::SetOverlayFileSize(ulong)

- ea: `0x1800098d0`
- end: `0x180009a49`
- name: `?SetOverlayFileSize@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `377`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c200`
- `0x18000c300`
- `0x1800169c4`

## callees

- `0x180007ad0`
- `0x180009848`
- `0x1800098d0`
- `0x18000a3ac`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009a23`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009a23`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180009a04`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180009a04`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::SetOverlayFileSize(CUwfStaticConfiguration *this, int a2)
{
  __int64 v2; // rsi
  int OverlayFileName; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+40h] [rbp-29h] BYREF
  __int128 v9; // [rsp+48h] [rbp-21h] BYREF
  __int128 v10; // [rsp+58h] [rbp-11h] BYREF
  __int128 v11; // [rsp+68h] [rbp-1h] BYREF
  __int128 v12; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v13; // [rsp+88h] [rbp+1Fh]
  __int128 v14; // [rsp+98h] [rbp+2Fh]
  HANDLE hFile; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v16; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = a2;
  hFile = 0;
  v16 = 0;
  OverlayFileName = CUwfStaticConfiguration::GetOverlayFileName(this, &v16);
  if ( OverlayFileName >= 0 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v11 = 0;
    v9 = 0;
    ((void (__fastcall *)(__int128 *, unsigned __int16 *))CNtCalls::s_pfnRtlInitUnicodeString)(&v9, v16);
    *(_QWORD *)&v13 = &v9;
    LODWORD(v12) = 48;
    *((_QWORD *)&v12 + 1) = 0;
    DWORD2(v13) = 0;
    v14 = 0;
    v5 = ((__int64 (__fastcall *)(HANDLE *, __int64, __int128 *, __int128 *, _DWORD, int))CNtCalls::s_pfnNtOpenFile)(
           &hFile,
           1310994,
           &v12,
           &v11,
           0,
           32866);
    OverlayFileName = v5 | 0x10000000;
    if ( v5 >= 0 )
    {
      v8 = v2 << 20;
      v10 = 0;
      v6 = ((__int64 (__fastcall *)(HANDLE, __int128 *, __int64 *, __int64, int))CNtCalls::s_pfnNtSetInformationFile)(
             hFile,
             &v10,
             &v8,
             8,
             20);
      OverlayFileName = v6 | 0x10000000;
      if ( v6 >= 0 )
      {
        OverlayFileName = v10 | 0x10000000;
        if ( (int)v10 >= 0 )
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
    }
  }
  if ( hFile )
    ((void (*)(void))CNtCalls::s_pfnNtClose)();
  operator delete[](v16);
  if ( OverlayFileName < 0 )
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = OverlayFileName;
  return (unsigned int)OverlayFileName;
}

```

## disassembly

```asm
0x1800098d0  mov     [rsp-8+arg_0], rbx
0x1800098d5  push    rbp
0x1800098d6  push    rsi
0x1800098d7  push    rdi
0x1800098d8  lea     rbp, [rsp-47h]
0x1800098dd  sub     rsp, 0B0h
0x1800098e4  movsxd  rsi, edx
0x1800098e7  mov     rdi, rcx
0x1800098ea  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x1800098ee  mov     [rbp+57h+hFile], 0
0x1800098f6  mov     [rbp+57h+arg_18], 0
0x1800098fe  call    ?GetOverlayFileName@CUwfStaticConfiguration@@QEAAJPEAPEAG@Z; CUwfStaticConfiguration::GetOverlayFileName(ushort * *)
0x180009903  mov     ebx, eax
0x180009905  test    eax, eax
0x180009907  js      loc_180009A0A
0x18000990d  mov     rdx, [rbp+57h+arg_18]
0x180009911  lea     rcx, [rbp+57h+var_78]
0x180009915  mov     rax, cs:?s_pfnRtlInitUnicodeString@CNtCalls@@0P6AXPEAU_UNICODE_STRING@@PEBG@ZEA; void (*CNtCalls::s_pfnRtlInitUnicodeString)(_UNICODE_STRING *,ushort const *)
0x18000991c  xorps   xmm0, xmm0
0x18000991f  xorps   xmm1, xmm1
0x180009922  movups  [rbp+57h+var_48], xmm0
0x180009926  movups  [rbp+57h+var_38], xmm0
0x18000992a  movups  [rbp+57h+var_28], xmm0
0x18000992e  movups  [rbp+57h+var_58], xmm0
0x180009932  movups  [rbp+57h+var_78], xmm1
0x180009936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993b  lea     rax, [rbp+57h+var_78]
0x18000993f  mov     [rsp+0C0h+var_98], 8062h
0x180009947  mov     qword ptr [rbp+57h+var_38], rax
0x18000994b  lea     r9, [rbp+57h+var_58]
0x18000994f  mov     rax, cs:?s_pfnNtOpenFile@CNtCalls@@0P6AJPEAPEAXKPEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@KK@ZEA; long (*CNtCalls::s_pfnNtOpenFile)(void * *,ulong,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,ulong,ulong)
0x180009956  lea     r8, [rbp+57h+var_48]
0x18000995a  xorps   xmm0, xmm0
0x18000995d  mov     dword ptr [rbp+57h+var_48], 30h ; '0'
0x180009964  mov     edx, 140112h
0x180009969  mov     qword ptr [rbp+57h+var_48+8], 0
0x180009971  lea     rcx, [rbp+57h+hFile]
0x180009975  mov     dword ptr [rbp+57h+var_38+8], 0
0x18000997c  movdqu  [rbp+57h+var_28], xmm0
0x180009981  mov     [rsp+0C0h+var_A0], 0
0x180009989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998e  mov     ebx, eax
0x180009990  or      ebx, 10000000h
0x180009996  jl      short loc_180009A0A
0x180009998  mov     rcx, [rbp+57h+hFile]
0x18000999c  lea     r8, [rbp+57h+var_80]
0x1800099a0  mov     rax, cs:?s_pfnNtSetInformationFile@CNtCalls@@0P6AJPEAXPEAU_IO_STATUS_BLOCK@@0KW4_FILE_INFORMATION_CLASS@@@ZEA; long (*CNtCalls::s_pfnNtSetInformationFile)(void *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x1800099a7  lea     rdx, [rbp+57h+var_68]
0x1800099ab  xorps   xmm0, xmm0
0x1800099ae  shl     rsi, 14h
0x1800099b2  mov     r9d, 8
0x1800099b8  mov     [rbp+57h+var_80], rsi
0x1800099bc  movups  [rbp+57h+var_68], xmm0
0x1800099c0  mov     [rsp+0C0h+var_A0], 14h
0x1800099c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cd  mov     ebx, eax
0x1800099cf  or      ebx, 10000000h
0x1800099d5  jl      short loc_180009A0A
0x1800099d7  mov     ebx, dword ptr [rbp+57h+var_68]
0x1800099da  or      ebx, 10000000h
0x1800099e0  jl      short loc_180009A0A
0x1800099e2  mov     rcx, [rbp+57h+hFile]; void *
0x1800099e6  call    ?UpdateOverlayFileHeader@@YAJPEAX@Z; UpdateOverlayFileHeader(void *)
0x1800099eb  mov     ebx, eax
0x1800099ed  test    eax, eax
0x1800099ef  js      short loc_180009A0A
0x1800099f1  mov     rcx, [rbp+57h+hFile]; Handle
0x1800099f5  call    ?SetOverlayFileSecurity@@YAJPEAX@Z; SetOverlayFileSecurity(void *)
0x1800099fa  mov     ebx, eax
0x1800099fc  test    eax, eax
0x1800099fe  js      short loc_180009A0A
0x180009a00  mov     rcx, [rbp+57h+hFile]; hFile
0x180009a04  call    cs:__imp_FlushFileBuffers
0x180009a0a  mov     rcx, [rbp+57h+hFile]
0x180009a0e  test    rcx, rcx
0x180009a11  jz      short loc_180009A1F
0x180009a13  mov     rax, cs:?s_pfnNtClose@CNtCalls@@0P6AJPEAX@ZEA; long (*CNtCalls::s_pfnNtClose)(void *)
0x180009a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a1f  mov     rcx, [rbp+57h+arg_18]
0x180009a23  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009a29  test    ebx, ebx
0x180009a2b  jns     short loc_180009A34
0x180009a2d  mov     rax, [rdi+20h]
0x180009a31  mov     [rax+10h], ebx
0x180009a34  mov     eax, ebx
0x180009a36  mov     rbx, [rsp+0C0h+arg_0]
0x180009a3e  add     rsp, 0B0h
0x180009a45  pop     rdi
0x180009a46  pop     rsi
0x180009a47  pop     rbp
0x180009a48  retn
```
