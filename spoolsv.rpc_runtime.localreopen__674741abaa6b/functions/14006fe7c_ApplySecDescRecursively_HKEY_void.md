# ApplySecDescRecursively(HKEY__ *,void *)

- ea: `0x14006fe7c`
- end: `0x14007003f`
- name: `?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z`
- size: `451`
- prototype: `unsigned int __fastcall(HKEY, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14006fe7c`
- `0x140070ebc`

## callees

- `0x14000b20c`
- `0x140013318`
- `0x140015378`
- `0x140018204`
- `0x14002e0dc`
- `0x14006fe7c`
- `0x1400702f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006ffc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006ffc7`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006fea0`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006fea0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006fefc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006fefc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006ff88`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006ff88`

## string_xrefs

- `0x14006fff6`: `Failed to set AppContainer permissions recursively, found a linked key %ws.`

## pseudocode

```c
__int64 __fastcall ApplySecDescRecursively(HKEY a1, void *a2)
{
  unsigned int v4; // ebx
  void *v5; // rax
  DWORD v6; // esi
  LSTATUS v7; // eax
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+48h] BYREF

  v4 = RegSetKeySecurity(a1, 4u, a2);
  if ( !v4 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v4 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v4 )
    {
      lpName = 0;
      v5 = operator new[](saturated_mul(++cbMaxSubKeyLen, 2u));
      NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&lpName, v5);
      v6 = 0;
      if ( !lpName )
        v4 = 8;
      while ( !v4 && v6 < cSubKeys )
      {
        cchName = cbMaxSubKeyLen;
        v7 = RegEnumKeyExW(a1, v6, lpName, &cchName, 0, 0, 0, 0);
        v4 = v7;
        if ( v7 )
        {
          if ( v7 == 259 )
          {
            v4 = 0;
            break;
          }
        }
        else if ( DeleteSymbolicLink(a1, lpName) )
        {
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "ApplySecDescRecursively",
            L"Failed to set AppContainer permissions recursively, found a linked key %ws.",
            lpName);
        }
        else
        {
          hKey[0] = 0;
          v4 = RegOpenKeyExW(a1, lpName, 0, 0xF003Fu, hKey);
          if ( !v4 )
            v4 = ApplySecDescRecursively(hKey[0], a2);
          NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(hKey);
        }
        ++v6;
      }
      NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&lpName);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14006fe7c  mov     [rsp-28h+arg_0], rbx
0x14006fe81  push    rbp
0x14006fe82  push    rsi
0x14006fe83  push    rdi
0x14006fe84  push    r12
0x14006fe86  push    r15
0x14006fe88  mov     rbp, rsp
0x14006fe8b  sub     rsp, 80h
0x14006fe92  mov     r15, rdx
0x14006fe95  mov     r8, rdx; pSecurityDescriptor
0x14006fe98  mov     edx, 4; SecurityInformation
0x14006fe9d  mov     rdi, rcx
0x14006fea0  call    cs:__imp_RegSetKeySecurity
0x14006fea7  nop     dword ptr [rax+rax+00h]
0x14006feac  xor     r12d, r12d
0x14006feaf  mov     ebx, eax
0x14006feb1  test    eax, eax
0x14006feb3  jnz     loc_140070025
0x14006feb9  mov     [rsp+80h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14006febe  lea     rax, [rbp+cbMaxSubKeyLen]
0x14006fec2  mov     [rsp+80h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14006fec7  xor     r9d, r9d; lpReserved
0x14006feca  mov     [rsp+80h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x14006fecf  xor     r8d, r8d; lpcchClass
0x14006fed2  mov     [rsp+80h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14006fed7  xor     edx, edx; lpClass
0x14006fed9  mov     [rsp+80h+lpcValues], r12; lpcValues
0x14006fede  mov     rcx, rdi; hKey
0x14006fee1  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14006fee6  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14006feeb  lea     rax, [rbp+cSubKeys]
0x14006feef  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x14006fef4  mov     [rbp+cSubKeys], r12d
0x14006fef8  mov     [rbp+cbMaxSubKeyLen], r12d
0x14006fefc  call    cs:__imp_RegQueryInfoKeyW
0x14006ff03  nop     dword ptr [rax+rax+00h]
0x14006ff08  mov     ebx, eax
0x14006ff0a  test    eax, eax
0x14006ff0c  jnz     loc_140070025
0x14006ff12  mov     eax, [rbp+cbMaxSubKeyLen]
0x14006ff15  inc     eax
0x14006ff17  mov     [rbp+lpName], r12
0x14006ff1b  mov     ecx, eax
0x14006ff1d  mov     [rbp+cbMaxSubKeyLen], eax
0x14006ff20  lea     eax, [rbx+2]
0x14006ff23  mul     rcx
0x14006ff26  lea     rcx, [r12-1]
0x14006ff2b  cmovb   rax, rcx
0x14006ff2f  mov     rcx, rax; unsigned __int64
0x14006ff32  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006ff37  mov     rdx, rax
0x14006ff3a  lea     rcx, [rbp+lpName]
0x14006ff3e  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x14006ff43  cmp     [rbp+lpName], r12
0x14006ff47  lea     eax, [rbx+8]
0x14006ff4a  mov     esi, r12d
0x14006ff4d  cmovz   ebx, eax
0x14006ff50  test    ebx, ebx
0x14006ff52  jnz     loc_14007001C
0x14006ff58  cmp     esi, [rbp+cSubKeys]
0x14006ff5b  jnb     loc_14007001C
0x14006ff61  mov     eax, [rbp+cbMaxSubKeyLen]
0x14006ff64  lea     r9, [rbp+cchName]; lpcchName
0x14006ff68  mov     r8, [rbp+lpName]; lpName
0x14006ff6c  mov     edx, esi; dwIndex
0x14006ff6e  mov     [rsp+80h+lpcValues], r12; lpftLastWriteTime
0x14006ff73  mov     rcx, rdi; hKey
0x14006ff76  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcchClass
0x14006ff7b  mov     [rsp+80h+lpcbMaxSubKeyLen], r12; lpClass
0x14006ff80  mov     [rsp+80h+lpcSubKeys], r12; lpReserved
0x14006ff85  mov     [rbp+cchName], eax
0x14006ff88  call    cs:__imp_RegEnumKeyExW
0x14006ff8f  nop     dword ptr [rax+rax+00h]
0x14006ff94  mov     ebx, eax
0x14006ff96  test    eax, eax
0x14006ff98  jnz     short loc_14007000B
0x14006ff9a  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x14006ff9e  mov     rcx, rdi; HKEY
0x14006ffa1  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x14006ffa6  test    eax, eax
0x14006ffa8  jnz     short loc_14006FFF2
0x14006ffaa  mov     rdx, [rbp+lpName]; lpSubKey
0x14006ffae  lea     rax, [rbp+hKey]
0x14006ffb2  mov     r9d, 0F003Fh; samDesired
0x14006ffb8  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x14006ffbd  xor     r8d, r8d; ulOptions
0x14006ffc0  mov     [rbp+hKey], r12
0x14006ffc4  mov     rcx, rdi; hKey
0x14006ffc7  call    cs:__imp_RegOpenKeyExW
0x14006ffce  nop     dword ptr [rax+rax+00h]
0x14006ffd3  mov     ebx, eax
0x14006ffd5  test    eax, eax
0x14006ffd7  jnz     short loc_14006FFE7
0x14006ffd9  mov     rcx, [rbp+hKey]; HKEY
0x14006ffdd  mov     rdx, r15; void *
0x14006ffe0  call    ?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z; ApplySecDescRecursively(HKEY__ *,void *)
0x14006ffe5  mov     ebx, eax
0x14006ffe7  lea     rcx, [rbp+hKey]
0x14006ffeb  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x14006fff0  jmp     short loc_140070012
0x14006fff2  mov     r8, [rbp+lpName]
0x14006fff6  lea     rdx, aFailedToSetApp; "Failed to set AppContainer permissions "...
0x14006fffd  lea     rcx, aApplysecdescre; "ApplySecDescRecursively"
0x140070004  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140070009  jmp     short loc_140070012
0x14007000b  cmp     eax, 103h
0x140070010  jz      short loc_140070019
0x140070012  inc     esi
0x140070014  jmp     loc_14006FF50
0x140070019  mov     ebx, r12d
0x14007001c  lea     rcx, [rbp+lpName]
0x140070020  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140070025  mov     eax, ebx
0x140070027  mov     rbx, [rsp+80h+arg_0]
0x14007002f  add     rsp, 80h
0x140070036  pop     r15
0x140070038  pop     r12
0x14007003a  pop     rdi
0x14007003b  pop     rsi
0x14007003c  pop     rbp
0x14007003d  retn
```
