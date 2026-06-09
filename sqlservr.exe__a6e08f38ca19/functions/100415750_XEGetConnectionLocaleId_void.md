# XEGetConnectionLocaleId(void)

- ea: `0x100415750`
- end: `0x100415826`
- name: `?XEGetConnectionLocaleId@@YAKXZ`
- size: `214`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x100415750`

## import_xrefs

- `sqlTsEs!?getmsglangid@@YAFF@Z` at `0x1004157d2`
- `sqlTsEs!?getmsglangid@@YAFF@Z` at `0x100415810`
- `sqlTsEs!?getmsglangid@@YAFF@Z` at `0x1004157d2`
- `sqlTsEs!?getmsglangid@@YAFF@Z` at `0x100415810`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004157de`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004157f6`
- `sqldk!SystemThread_TlsOffset` at `0x10041575d`
- `sqldk!SystemThread_TlsIndex` at `0x100415754`

## pseudocode

```c
unsigned int XEGetConnectionLocaleId(void)
{
  __int64 v1; // rax

  if ( *(_QWORD *)(SystemThread_TlsOffset
                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))
    && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 120LL)
    && **(_QWORD **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset)
                   + 64LL) )
  {
    return getmsglangid(*(_WORD *)(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset)
                                               + 64LL)
                                 + 16LL));
  }
  if ( !(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf) )
    return 1033;
  v1 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  return getmsglangid(*(_WORD *)(v1 + 154));
}

```

## disassembly

```asm
0x100415750  sub     rsp, 28h
0x100415754  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041575b  mov     ecx, [rax]
0x10041575d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100415764  lea     rdx, ds:0[rcx*8]
0x10041576c  mov     r8d, [rax]
0x10041576f  mov     rax, gs:58h
0x100415778  mov     rcx, [rax+rdx]
0x10041577c  cmp     qword ptr [r8+rcx], 0
0x100415781  jz      short loc_1004157DE
0x100415783  mov     rax, gs:58h
0x10041578c  mov     rcx, [rax+rdx]
0x100415790  mov     rax, [rcx+r8]
0x100415794  cmp     qword ptr [rax+78h], 0
0x100415799  jz      short loc_1004157DE
0x10041579b  mov     rax, gs:58h
0x1004157a4  mov     rcx, [rax+rdx]
0x1004157a8  mov     rax, [rcx+r8]
0x1004157ac  mov     rcx, [rax+40h]
0x1004157b0  cmp     qword ptr [rcx], 0
0x1004157b4  jz      short loc_1004157DE
0x1004157b6  mov     rax, gs:58h
0x1004157bf  mov     rcx, [rax+rdx]
0x1004157c3  mov     rax, [rcx+r8]
0x1004157c7  mov     rcx, [rax+40h]
0x1004157cb  mov     rax, [rcx]
0x1004157ce  movzx   ecx, word ptr [rax+10h]
0x1004157d2  call    cs:__imp_?getmsglangid@@YAFF@Z; getmsglangid(short)
0x1004157d8  cwde
0x1004157d9  add     rsp, 28h
0x1004157dd  retn
0x1004157de  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1004157e5  mov     rcx, [rax]
0x1004157e8  mov     rax, [rcx]
0x1004157eb  call    qword ptr [rax+1F8h]
0x1004157f1  test    rax, rax
0x1004157f4  jz      short loc_10041581C
0x1004157f6  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1004157fd  mov     rcx, [rax]
0x100415800  mov     rax, [rcx]
0x100415803  call    qword ptr [rax+1F8h]
0x100415809  movzx   ecx, word ptr [rax+9Ah]
0x100415810  call    cs:__imp_?getmsglangid@@YAFF@Z; getmsglangid(short)
0x100415816  cwde
0x100415817  add     rsp, 28h
0x10041581b  retn
0x10041581c  mov     eax, 409h
0x100415821  add     rsp, 28h
0x100415825  retn
```
