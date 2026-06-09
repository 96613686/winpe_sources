# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180029f10`
- end: `0x18002a040`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `304`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180027a64`
- `0x180029f10`
- `0x18002a764`
- `0x18002acec`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180029f60`
- `KERNEL32!GetWindowsDirectoryW` at `0x180029f60`

## string_xrefs

- `0x180029f8a`: `*.xml`
- `0x180029fb1`: `*.ptxml`
- `0x180029f70`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ecx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetWindowsDirectoryW(Buffer, 0x104u)
      && (int)StringCchCatW(Buffer, 0x104u, L"\\system32\\wdi\\PerfTrack\\") >= 0 )
    {
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.xml");
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.ptxml");
    }
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(this, a2, a3, a4);
  }
  v8 = *((_QWORD *)this + 1);
  if ( v8 )
    v9 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v8 + 96LL))(
           v8,
           a2,
           a3,
           a4);
  else
    v9 = 1;
  if ( !*((_BYTE *)this + 32) && v9 == -2147467263 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x180029f10  push    rbx
0x180029f12  push    rbp
0x180029f13  push    rsi
0x180029f14  push    rdi
0x180029f15  sub     rsp, 258h
0x180029f1c  mov     rax, cs:__security_cookie
0x180029f23  xor     rax, rsp
0x180029f26  mov     [rsp+278h+var_38], rax
0x180029f2e  cmp     byte ptr [rcx+20h], 0
0x180029f32  mov     ebp, r9d
0x180029f35  mov     esi, r8d
0x180029f38  mov     rbx, rdx
0x180029f3b  mov     rdi, rcx
0x180029f3e  jnz     loc_180029FE9
0x180029f44  xor     edx, edx; Val
0x180029f46  lea     rcx, [rsp+278h+Buffer]; void *
0x180029f4b  mov     r8d, 208h; Size
0x180029f51  call    memset_0
0x180029f56  mov     edx, 104h; uSize
0x180029f5b  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x180029f60  call    cs:__imp_GetWindowsDirectoryW
0x180029f67  nop     dword ptr [rax+rax+00h]
0x180029f6c  test    eax, eax
0x180029f6e  jz      short loc_180029FD8
0x180029f70  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x180029f77  mov     edx, 104h; unsigned __int64
0x180029f7c  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x180029f81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029f86  test    eax, eax
0x180029f88  js      short loc_180029FD8
0x180029f8a  lea     rax, aXml; "*.xml"
0x180029f91  mov     r9d, ebp; unsigned int
0x180029f94  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x180029f99  mov     r8d, esi; unsigned int
0x180029f9c  lea     rax, [rsp+278h+Buffer]
0x180029fa1  mov     rdx, rbx; union _LARGE_INTEGER
0x180029fa4  mov     rcx, rdi; this
0x180029fa7  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x180029fac  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x180029fb1  lea     rax, aPtxml; "*.ptxml"
0x180029fb8  mov     r9d, ebp; unsigned int
0x180029fbb  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x180029fc0  mov     r8d, esi; unsigned int
0x180029fc3  lea     rax, [rsp+278h+Buffer]
0x180029fc8  mov     rdx, rbx; union _LARGE_INTEGER
0x180029fcb  mov     rcx, rdi; this
0x180029fce  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x180029fd3  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x180029fd8  mov     r9d, ebp; unsigned int
0x180029fdb  mov     r8d, esi; unsigned int
0x180029fde  mov     rdx, rbx; union _LARGE_INTEGER
0x180029fe1  mov     rcx, rdi; this
0x180029fe4  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x180029fe9  mov     rcx, [rdi+8]
0x180029fed  test    rcx, rcx
0x180029ff0  jz      short loc_18002A00B
0x180029ff2  mov     rax, [rcx]
0x180029ff5  mov     r9d, ebp
0x180029ff8  mov     r8d, esi
0x180029ffb  mov     rdx, rbx
0x180029ffe  mov     rax, [rax+60h]
0x18002a002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a007  mov     ecx, eax
0x18002a009  jmp     short loc_18002A010
0x18002a00b  mov     ecx, 1
0x18002a010  cmp     byte ptr [rdi+20h], 0
0x18002a014  jnz     short loc_18002A021
0x18002a016  xor     eax, eax
0x18002a018  cmp     ecx, 80004001h
0x18002a01e  cmovz   ecx, eax
0x18002a021  mov     eax, ecx
0x18002a023  mov     rcx, [rsp+278h+var_38]
0x18002a02b  xor     rcx, rsp; StackCookie
0x18002a02e  call    __security_check_cookie
0x18002a033  add     rsp, 258h
0x18002a03a  pop     rdi
0x18002a03b  pop     rsi
0x18002a03c  pop     rbp
0x18002a03d  pop     rbx
0x18002a03e  retn
```
