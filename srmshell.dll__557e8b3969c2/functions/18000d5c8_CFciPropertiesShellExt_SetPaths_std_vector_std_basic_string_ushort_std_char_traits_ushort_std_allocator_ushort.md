# CFciPropertiesShellExt::SetPaths(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000d5c8`
- end: `0x18000d687`
- name: `?SetPaths@CFciPropertiesShellExt@@QEAAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `191`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800096c0`
- `0x18000dd70`

## callees

- `0x1800052b0`
- `0x18000d5c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d5f1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d5f1`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::SetPaths(__int64 a1, __int64 *a2)
{
  int v4; // ebp
  __int64 i; // rbx
  const WCHAR *v6; // rcx
  DWORD FileAttributesW; // eax
  bool v8; // zf
  int v9; // eax
  __int64 *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  CFciPropertiesShellExt::PropertyInfo *v14; // rbx
  CFciPropertiesShellExt::PropertyInfo *v15; // rbp
  CFciPropertiesShellExt::PropertyInfo *v16; // rsi

  v4 = 0;
  for ( i = *a2; i != a2[1]; i += 40 )
  {
    if ( *(_QWORD *)(i + 24) < 8u )
      v6 = (const WCHAR *)i;
    else
      v6 = *(const WCHAR **)i;
    FileAttributesW = GetFileAttributesW(v6);
    if ( FileAttributesW == -1 || (v8 = (FileAttributesW & 0x10) == 0, v9 = 2, v8) )
      v9 = 1;
    v4 |= v9;
  }
  v10 = (__int64 *)(a1 + 24);
  if ( (__int64 *)(a1 + 24) != a2 )
  {
    v11 = *v10;
    *v10 = *a2;
    *a2 = v11;
    v12 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = a2[1];
    a2[1] = v12;
    v13 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = a2[2];
    a2[2] = v13;
  }
  *(_DWORD *)(a1 + 244) = v4;
  v14 = *(CFciPropertiesShellExt::PropertyInfo **)(a1 + 64);
  v15 = *(CFciPropertiesShellExt::PropertyInfo **)(a1 + 72);
  if ( v14 != v15 )
  {
    v16 = *(CFciPropertiesShellExt::PropertyInfo **)(a1 + 64);
    do
    {
      CFciPropertiesShellExt::PropertyInfo::~PropertyInfo(v16);
      v16 = (CFciPropertiesShellExt::PropertyInfo *)((char *)v16 + 224);
    }
    while ( v16 != v15 );
    *(_QWORD *)(a1 + 72) = v14;
  }
  *(_WORD *)(a1 + 216) = 0;
}

```

## disassembly

```asm
0x18000d5c8  push    rbx
0x18000d5ca  push    rbp
0x18000d5cb  push    rsi
0x18000d5cc  push    rdi
0x18000d5cd  sub     rsp, 28h
0x18000d5d1  mov     rsi, rdx
0x18000d5d4  mov     rdi, rcx
0x18000d5d7  xor     ebp, ebp
0x18000d5d9  mov     rbx, [rdx]
0x18000d5dc  cmp     rbx, [rsi+8]
0x18000d5e0  jz      short loc_18000D612
0x18000d5e2  cmp     qword ptr [rbx+18h], 8
0x18000d5e7  jb      short loc_18000D5EE
0x18000d5e9  mov     rcx, [rbx]
0x18000d5ec  jmp     short loc_18000D5F1
0x18000d5ee  mov     rcx, rbx; lpFileName
0x18000d5f1  call    cs:__imp_GetFileAttributesW
0x18000d5f7  cmp     eax, 0FFFFFFFFh
0x18000d5fa  jz      short loc_18000D605
0x18000d5fc  test    al, 10h
0x18000d5fe  mov     eax, 2
0x18000d603  jnz     short loc_18000D60A
0x18000d605  mov     eax, 1
0x18000d60a  add     rbx, 28h ; '('
0x18000d60e  or      ebp, eax
0x18000d610  jmp     short loc_18000D5DC
0x18000d612  lea     rdx, [rdi+18h]
0x18000d616  cmp     rdx, rsi
0x18000d619  jz      short loc_18000D647
0x18000d61b  mov     rcx, [rdx]
0x18000d61e  mov     rax, [rsi]
0x18000d621  mov     [rdx], rax
0x18000d624  mov     [rsi], rcx
0x18000d627  mov     rcx, [rdx+8]
0x18000d62b  mov     rax, [rsi+8]
0x18000d62f  mov     [rdx+8], rax
0x18000d633  mov     [rsi+8], rcx
0x18000d637  mov     rcx, [rdx+10h]
0x18000d63b  mov     rax, [rsi+10h]
0x18000d63f  mov     [rdx+10h], rax
0x18000d643  mov     [rsi+10h], rcx
0x18000d647  mov     [rdi+0F4h], ebp
0x18000d64d  mov     rbx, [rdi+40h]
0x18000d651  mov     rbp, [rdi+48h]
0x18000d655  cmp     rbx, rbp
0x18000d658  jz      short loc_18000D675
0x18000d65a  mov     rsi, rbx
0x18000d65d  mov     rcx, rsi; this
0x18000d660  call    ??1PropertyInfo@CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::PropertyInfo::~PropertyInfo(void)
0x18000d665  add     rsi, 0E0h
0x18000d66c  cmp     rsi, rbp
0x18000d66f  jnz     short loc_18000D65D
0x18000d671  mov     [rdi+48h], rbx
0x18000d675  mov     word ptr [rdi+0D8h], 0
0x18000d67e  add     rsp, 28h
0x18000d682  pop     rdi
0x18000d683  pop     rsi
0x18000d684  pop     rbp
0x18000d685  pop     rbx
0x18000d686  retn
```
