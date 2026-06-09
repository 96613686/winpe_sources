# CAssemblyCacheItem::~CAssemblyCacheItem(void)

- ea: `0x18005db38`
- end: `0x18005dbcf`
- name: `??1CAssemblyCacheItem@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CAssemblyCacheItem *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180060eec`

## callees

- `0x18000c000`
- `0x180014260`
- `0x18001e5d0`
- `0x18005db38`
- `0x1800683a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005db93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005db93`

## string_xrefs

- `0x18005db80`: `SXS.DLL: SxspDeleteDirectory returns FALSE\n`

## pseudocode

```c
void __fastcall CAssemblyCacheItem::~CAssemblyCacheItem(CAssemblyCacheItem *this)
{
  DWORD LastError; // ebx

  *(_QWORD *)this = &CAssemblyCacheItem::`vftable';
  LastError = GetLastError();
  if ( **((_WORD **)this + 6) && *((_DWORD *)this + 5) == 1 && !(unsigned int)SxspDeleteDirectory((char *)this + 32) )
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: SxspDeleteDirectory returns FALSE\n");
  SetLastError(LastError);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>((char *)this + 760);
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>((char *)this + 592);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>((char *)this + 32);
}

```

## disassembly

```asm
0x18005db38  mov     [rsp+arg_0], rbx
0x18005db3d  mov     [rsp+arg_8], rsi
0x18005db42  push    rdi
0x18005db43  sub     rsp, 20h
0x18005db47  lea     rax, ??_7CAssemblyCacheItem@@6B@; const CAssemblyCacheItem::`vftable'
0x18005db4e  mov     rdi, rcx
0x18005db51  mov     [rcx], rax
0x18005db54  call    cs:__imp_GetLastError
0x18005db5b  nop     dword ptr [rax+rax+00h]
0x18005db60  mov     ebx, eax
0x18005db62  xor     esi, esi
0x18005db64  mov     rax, [rdi+30h]
0x18005db68  cmp     [rax], si
0x18005db6b  jz      short loc_18005DB91
0x18005db6d  cmp     dword ptr [rdi+14h], 1
0x18005db71  jnz     short loc_18005DB91
0x18005db73  lea     rcx, [rdi+20h]
0x18005db77  call    ?SxspDeleteDirectory@@YAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspDeleteDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x18005db7c  test    eax, eax
0x18005db7e  jnz     short loc_18005DB91
0x18005db80  lea     rdx, aSxsDllSxspdele; "SXS.DLL: SxspDeleteDirectory returns FA"...
0x18005db87  mov     ecx, 0C0000000h; unsigned int
0x18005db8c  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18005db91  mov     ecx, ebx; dwErrCode
0x18005db93  call    cs:__imp_SetLastError
0x18005db9a  nop     dword ptr [rax+rax+00h]
0x18005db9f  lea     rcx, [rdi+2F8h]; void *
0x18005dba6  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005dbab  lea     rcx, [rdi+250h]
0x18005dbb2  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005dbb7  lea     rcx, [rdi+20h]; void *
0x18005dbbb  mov     rbx, [rsp+28h+arg_0]
0x18005dbc0  mov     rsi, [rsp+28h+arg_8]
0x18005dbc5  add     rsp, 20h
0x18005dbc9  pop     rdi
0x18005dbca  jmp     ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
```
