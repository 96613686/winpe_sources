# WsDestroyUseStructures

- ea: `0x18002a54c`
- end: `0x18002a63d`
- name: `WsDestroyUseStructures`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18002db4c`

## callees

- `0x180008a4c`
- `0x180008c90`
- `0x18002a54c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002a564`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a564`
- `ntdll!RtlReleaseResource` at `0x18002a600`
- `ntdll!RtlReleaseResource` at `0x18002a600`
- `ntdll!RtlDeleteResource` at `0x18002a627`
- `ntdll!RtlDeleteResource` at `0x18002a627`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x18002a60d`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x18002a60d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a61a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a61a`

## pseudocode

```c
void WsDestroyUseStructures()
{
  unsigned int v0; // ecx
  __int64 i; // rdi
  _QWORD *v2; // rbx
  _DWORD *v3; // rcx
  void *v4; // rcx

  if ( RtlAcquireResourceExclusive(&Resource, 1u) )
  {
    v0 = dword_18004F110;
    for ( i = 0; (unsigned int)i < v0; i = (unsigned int)(i + 1) )
    {
      v2 = *(_QWORD **)(Use + 24 * i);
      if ( v2 )
      {
        do
        {
          WsDeleteConnectionEx((PLUID)(Use + 8 + 24 * i), (HANDLE)v2[4], 0, 1);
          WsDeleteSymbolicLink(v2[2], (const WCHAR *)v2[6], 0, (void *)0xFFFFFFFFFFFFFFFFLL);
          *(_DWORD *)v2[1] -= *((_DWORD *)v2 + 7);
          v3 = (_DWORD *)v2[1];
          if ( !*v3 )
            LocalFree(v3);
          v4 = v2;
          v2 = (_QWORD *)*v2;
          LocalFree(v4);
        }
        while ( v2 );
        v0 = dword_18004F110;
      }
    }
    RtlReleaseResource(&Resource);
    LocalUnlock(qword_18004F108);
    LocalFree(qword_18004F108);
    RtlDeleteResource(&Resource);
  }
}

```

## disassembly

```asm
0x18002a54c  mov     [rsp+arg_0], rbx
0x18002a551  mov     [rsp+arg_8], rsi
0x18002a556  push    rdi
0x18002a557  sub     rsp, 20h
0x18002a55b  mov     dl, 1; Wait
0x18002a55d  lea     rcx, Resource; Resource
0x18002a564  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a56a  test    al, al
0x18002a56c  jz      loc_18002A62D
0x18002a572  mov     ecx, cs:dword_18004F110
0x18002a578  xor     edi, edi
0x18002a57a  test    ecx, ecx
0x18002a57c  jz      short loc_18002A5F9
0x18002a57e  mov     rax, cs:Use
0x18002a585  lea     rsi, [rdi+rdi*2]
0x18002a589  mov     rbx, [rax+rsi*8]
0x18002a58d  test    rbx, rbx
0x18002a590  jz      short loc_18002A5F3
0x18002a592  mov     rcx, cs:Use
0x18002a599  mov     r9b, 1
0x18002a59c  mov     rdx, [rbx+20h]; Handle
0x18002a5a0  add     rcx, 8
0x18002a5a4  xor     r8d, r8d
0x18002a5a7  lea     rcx, [rcx+rsi*8]; SourceLuid
0x18002a5ab  call    WsDeleteConnectionEx
0x18002a5b0  mov     rdx, [rbx+30h]
0x18002a5b4  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002a5b8  mov     rcx, [rbx+10h]
0x18002a5bc  xor     r8d, r8d
0x18002a5bf  call    WsDeleteSymbolicLink
0x18002a5c4  mov     rcx, [rbx+8]
0x18002a5c8  mov     eax, [rbx+1Ch]
0x18002a5cb  sub     [rcx], eax
0x18002a5cd  mov     rcx, [rbx+8]; hMem
0x18002a5d1  cmp     dword ptr [rcx], 0
0x18002a5d4  jnz     short loc_18002A5DC
0x18002a5d6  call    cs:__imp_LocalFree
0x18002a5dc  mov     rcx, rbx; hMem
0x18002a5df  mov     rbx, [rbx]
0x18002a5e2  call    cs:__imp_LocalFree
0x18002a5e8  test    rbx, rbx
0x18002a5eb  jnz     short loc_18002A592
0x18002a5ed  mov     ecx, cs:dword_18004F110
0x18002a5f3  inc     edi
0x18002a5f5  cmp     edi, ecx
0x18002a5f7  jb      short loc_18002A57E
0x18002a5f9  lea     rcx, Resource; Resource
0x18002a600  call    cs:__imp_RtlReleaseResource
0x18002a606  mov     rcx, cs:qword_18004F108; hMem
0x18002a60d  call    cs:__imp_LocalUnlock
0x18002a613  mov     rcx, cs:qword_18004F108; hMem
0x18002a61a  call    cs:__imp_LocalFree
0x18002a620  lea     rcx, Resource; Resource
0x18002a627  call    cs:__imp_RtlDeleteResource
0x18002a62d  mov     rbx, [rsp+28h+arg_0]
0x18002a632  mov     rsi, [rsp+28h+arg_8]
0x18002a637  add     rsp, 20h
0x18002a63b  pop     rdi
0x18002a63c  retn
```
