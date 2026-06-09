# ApplySecDescRecursively(HKEY__ *,void *)

- ea: `0x1400694d8`
- end: `0x140069682`
- name: `?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z`
- size: `426`
- prototype: `unsigned int __fastcall(HKEY, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400694d8`
- `0x14006a3dc`

## callees

- `0x14000a398`
- `0x14001246c`
- `0x1400140cc`
- `0x140016d54`
- `0x14002bbcc`
- `0x1400694d8`
- `0x140069910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140069611`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140069611`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400694fc`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400694fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140069552`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140069552`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400695d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400695d8`

## string_xrefs

- `0x14006963a`: `Failed to set AppContainer permissions recursively, found a linked key %ws.`

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
0x1400694d8  mov     [rsp-28h+arg_0], rbx
0x1400694dd  push    rbp
0x1400694de  push    rsi
0x1400694df  push    rdi
0x1400694e0  push    r12
0x1400694e2  push    r15
0x1400694e4  mov     rbp, rsp
0x1400694e7  sub     rsp, 80h
0x1400694ee  mov     r15, rdx
0x1400694f1  mov     r8, rdx; pSecurityDescriptor
0x1400694f4  mov     edx, 4; SecurityInformation
0x1400694f9  mov     rdi, rcx
0x1400694fc  call    cs:__imp_RegSetKeySecurity
0x140069502  xor     r12d, r12d
0x140069505  mov     ebx, eax
0x140069507  test    eax, eax
0x140069509  jnz     loc_140069669
0x14006950f  mov     [rsp+80h+lpftLastWriteTime], r12; lpftLastWriteTime
0x140069514  lea     rax, [rbp+cbMaxSubKeyLen]
0x140069518  mov     [rsp+80h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14006951d  xor     r9d, r9d; lpReserved
0x140069520  mov     [rsp+80h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x140069525  xor     r8d, r8d; lpcchClass
0x140069528  mov     [rsp+80h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14006952d  xor     edx, edx; lpClass
0x14006952f  mov     [rsp+80h+lpcValues], r12; lpcValues
0x140069534  mov     rcx, rdi; hKey
0x140069537  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14006953c  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140069541  lea     rax, [rbp+cSubKeys]
0x140069545  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x14006954a  mov     [rbp+cSubKeys], r12d
0x14006954e  mov     [rbp+cbMaxSubKeyLen], r12d
0x140069552  call    cs:__imp_RegQueryInfoKeyW
0x140069558  mov     ebx, eax
0x14006955a  test    eax, eax
0x14006955c  jnz     loc_140069669
0x140069562  mov     eax, [rbp+cbMaxSubKeyLen]
0x140069565  inc     eax
0x140069567  mov     [rbp+lpName], r12
0x14006956b  mov     ecx, eax
0x14006956d  mov     [rbp+cbMaxSubKeyLen], eax
0x140069570  lea     eax, [rbx+2]
0x140069573  mul     rcx
0x140069576  lea     rcx, [r12-1]
0x14006957b  cmovb   rax, rcx
0x14006957f  mov     rcx, rax; unsigned __int64
0x140069582  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140069587  mov     rdx, rax
0x14006958a  lea     rcx, [rbp+lpName]
0x14006958e  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x140069593  cmp     [rbp+lpName], r12
0x140069597  lea     eax, [rbx+8]
0x14006959a  mov     esi, r12d
0x14006959d  cmovz   ebx, eax
0x1400695a0  test    ebx, ebx
0x1400695a2  jnz     loc_140069660
0x1400695a8  cmp     esi, [rbp+cSubKeys]
0x1400695ab  jnb     loc_140069660
0x1400695b1  mov     eax, [rbp+cbMaxSubKeyLen]
0x1400695b4  lea     r9, [rbp+cchName]; lpcchName
0x1400695b8  mov     r8, [rbp+lpName]; lpName
0x1400695bc  mov     edx, esi; dwIndex
0x1400695be  mov     [rsp+80h+lpcValues], r12; lpftLastWriteTime
0x1400695c3  mov     rcx, rdi; hKey
0x1400695c6  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcchClass
0x1400695cb  mov     [rsp+80h+lpcbMaxSubKeyLen], r12; lpClass
0x1400695d0  mov     [rsp+80h+lpcSubKeys], r12; lpReserved
0x1400695d5  mov     [rbp+cchName], eax
0x1400695d8  call    cs:__imp_RegEnumKeyExW
0x1400695de  mov     ebx, eax
0x1400695e0  test    eax, eax
0x1400695e2  jnz     short loc_14006964F
0x1400695e4  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x1400695e8  mov     rcx, rdi; HKEY
0x1400695eb  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x1400695f0  test    eax, eax
0x1400695f2  jnz     short loc_140069636
0x1400695f4  mov     rdx, [rbp+lpName]; lpSubKey
0x1400695f8  lea     rax, [rbp+hKey]
0x1400695fc  mov     r9d, 0F003Fh; samDesired
0x140069602  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x140069607  xor     r8d, r8d; ulOptions
0x14006960a  mov     [rbp+hKey], r12
0x14006960e  mov     rcx, rdi; hKey
0x140069611  call    cs:__imp_RegOpenKeyExW
0x140069617  mov     ebx, eax
0x140069619  test    eax, eax
0x14006961b  jnz     short loc_14006962B
0x14006961d  mov     rcx, [rbp+hKey]; HKEY
0x140069621  mov     rdx, r15; void *
0x140069624  call    ?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z; ApplySecDescRecursively(HKEY__ *,void *)
0x140069629  mov     ebx, eax
0x14006962b  lea     rcx, [rbp+hKey]
0x14006962f  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x140069634  jmp     short loc_140069656
0x140069636  mov     r8, [rbp+lpName]
0x14006963a  lea     rdx, aFailedToSetApp; "Failed to set AppContainer permissions "...
0x140069641  lea     rcx, aApplysecdescre; "ApplySecDescRecursively"
0x140069648  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006964d  jmp     short loc_140069656
0x14006964f  cmp     eax, 103h
0x140069654  jz      short loc_14006965D
0x140069656  inc     esi
0x140069658  jmp     loc_1400695A0
0x14006965d  mov     ebx, r12d
0x140069660  lea     rcx, [rbp+lpName]
0x140069664  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140069669  mov     eax, ebx
0x14006966b  mov     rbx, [rsp+80h+arg_0]
0x140069673  add     rsp, 80h
0x14006967a  pop     r15
0x14006967c  pop     r12
0x14006967e  pop     rdi
0x14006967f  pop     rsi
0x140069680  pop     rbp
0x140069681  retn
```
