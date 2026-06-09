# WsDestroyUseStructures

- ea: `0x18002cac8`
- end: `0x18002cbec`
- name: `WsDestroyUseStructures`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180030544`

## callees

- `0x180009110`
- `0x180009370`
- `0x18002cac8`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002cae0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002cae0`
- `ntdll!RtlReleaseResource` at `0x18002cb96`
- `ntdll!RtlReleaseResource` at `0x18002cb96`
- `ntdll!RtlDeleteResource` at `0x18002cbcf`
- `ntdll!RtlDeleteResource` at `0x18002cbcf`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x18002cba9`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x18002cba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbbc`

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
    v0 = dword_180052110;
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
        v0 = dword_180052110;
      }
    }
    RtlReleaseResource(&Resource);
    LocalUnlock(qword_180052108);
    LocalFree(qword_180052108);
    RtlDeleteResource(&Resource);
  }
}

```

## disassembly

```asm
0x18002cac8  mov     [rsp+arg_0], rbx
0x18002cacd  mov     [rsp+arg_8], rsi
0x18002cad2  push    rdi
0x18002cad3  sub     rsp, 20h
0x18002cad7  mov     dl, 1; Wait
0x18002cad9  lea     rcx, Resource; Resource
0x18002cae0  call    cs:__imp_RtlAcquireResourceExclusive
0x18002cae7  nop     dword ptr [rax+rax+00h]
0x18002caec  test    al, al
0x18002caee  jz      loc_18002CBDB
0x18002caf4  mov     ecx, cs:dword_180052110
0x18002cafa  xor     edi, edi
0x18002cafc  test    ecx, ecx
0x18002cafe  jz      loc_18002CB8F
0x18002cb04  mov     rax, cs:Use
0x18002cb0b  lea     rsi, [rdi+rdi*2]
0x18002cb0f  mov     rbx, [rax+rsi*8]
0x18002cb13  test    rbx, rbx
0x18002cb16  jz      short loc_18002CB85
0x18002cb18  mov     rcx, cs:Use
0x18002cb1f  mov     r9b, 1
0x18002cb22  mov     rdx, [rbx+20h]; Handle
0x18002cb26  add     rcx, 8
0x18002cb2a  xor     r8d, r8d
0x18002cb2d  lea     rcx, [rcx+rsi*8]; SourceLuid
0x18002cb31  call    WsDeleteConnectionEx
0x18002cb36  mov     rdx, [rbx+30h]
0x18002cb3a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002cb3e  mov     rcx, [rbx+10h]
0x18002cb42  xor     r8d, r8d
0x18002cb45  call    WsDeleteSymbolicLink
0x18002cb4a  mov     rcx, [rbx+8]
0x18002cb4e  mov     eax, [rbx+1Ch]
0x18002cb51  sub     [rcx], eax
0x18002cb53  mov     rcx, [rbx+8]; hMem
0x18002cb57  cmp     dword ptr [rcx], 0
0x18002cb5a  jnz     short loc_18002CB68
0x18002cb5c  call    cs:__imp_LocalFree
0x18002cb63  nop     dword ptr [rax+rax+00h]
0x18002cb68  mov     rcx, rbx; hMem
0x18002cb6b  mov     rbx, [rbx]
0x18002cb6e  call    cs:__imp_LocalFree
0x18002cb75  nop     dword ptr [rax+rax+00h]
0x18002cb7a  test    rbx, rbx
0x18002cb7d  jnz     short loc_18002CB18
0x18002cb7f  mov     ecx, cs:dword_180052110
0x18002cb85  inc     edi
0x18002cb87  cmp     edi, ecx
0x18002cb89  jb      loc_18002CB04
0x18002cb8f  lea     rcx, Resource; Resource
0x18002cb96  call    cs:__imp_RtlReleaseResource
0x18002cb9d  nop     dword ptr [rax+rax+00h]
0x18002cba2  mov     rcx, cs:qword_180052108; hMem
0x18002cba9  call    cs:__imp_LocalUnlock
0x18002cbb0  nop     dword ptr [rax+rax+00h]
0x18002cbb5  mov     rcx, cs:qword_180052108; hMem
0x18002cbbc  call    cs:__imp_LocalFree
0x18002cbc3  nop     dword ptr [rax+rax+00h]
0x18002cbc8  lea     rcx, Resource; Resource
0x18002cbcf  call    cs:__imp_RtlDeleteResource
0x18002cbd6  nop     dword ptr [rax+rax+00h]
0x18002cbdb  mov     rbx, [rsp+28h+arg_0]
0x18002cbe0  mov     rsi, [rsp+28h+arg_8]
0x18002cbe5  add     rsp, 20h
0x18002cbe9  pop     rdi
0x18002cbea  retn
```
