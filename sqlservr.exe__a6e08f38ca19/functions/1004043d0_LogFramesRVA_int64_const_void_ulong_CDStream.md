# LogFramesRVA(__int64 (*const *)(void),ulong,CDStream *)

- ea: `0x1004043d0`
- end: `0x1004044af`
- name: `?LogFramesRVA@@YAXPEBQ6A_JXZKPEAVCDStream@@@Z`
- size: `223`
- prototype: `void __fastcall(__int64 (*const *)(void), unsigned int, struct CDStream *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x100405b20`
- `0x100406350`
- `0x100406750`
- `0x100406c30`

## callees

- `0x100401580`
- `0x1004043d0`
- `0x10044c870`

## import_xrefs

- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100404441`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x100404432`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x100404486`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x100404486`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10040446e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10040446e`

## pseudocode

```c
void __fastcall LogFramesRVA(__int64 (*const *a1)(void), unsigned int a2, struct CDStream *a3)
{
  unsigned int i; // ebx
  const void *v7; // rdx
  void (*v8)(const wchar_t *, ...); // r8
  unsigned __int64 v9; // [rsp+20h] [rbp-148h] BYREF
  char *v10; // [rsp+28h] [rbp-140h] BYREF
  char v11[272]; // [rsp+30h] [rbp-138h] BYREF

  for ( i = 0; i < a2; ++a1 )
  {
    v7 = *a1;
    v10 = v11;
    v9 = 260;
    XE_FormatModuleAndOffsetFromAddress(i, v7, &v10, &v9);
    if ( v9 != 260 )
    {
      v8 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v8 = SOS_OS_LogUnlocalizedRoutine;
      v8(L"%hs", v11);
      if ( a3 )
        CDStream::Write(a3, "Frame", v11);
    }
    ++i;
  }
  if ( a3 )
    CDStream::Flush(a3);
}

```

## disassembly

```asm
0x1004043d0  mov     [rsp+arg_8], rbx
0x1004043d5  push    rbp
0x1004043d6  push    rsi
0x1004043d7  push    rdi
0x1004043d8  sub     rsp, 150h
0x1004043df  mov     rax, cs:__security_cookie
0x1004043e6  xor     rax, rsp
0x1004043e9  mov     [rsp+168h+var_28], rax
0x1004043f1  xor     ebx, ebx
0x1004043f3  mov     rsi, r8
0x1004043f6  mov     ebp, edx
0x1004043f8  mov     rdi, rcx
0x1004043fb  test    edx, edx
0x1004043fd  jz      short loc_10040447E
0x1004043ff  nop
0x100404400  mov     rdx, [rdi]; void *
0x100404403  lea     rax, [rsp+168h+var_138]
0x100404408  lea     r9, [rsp+168h+var_148]; unsigned __int64 *
0x10040440d  mov     [rsp+168h+var_140], rax
0x100404412  lea     r8, [rsp+168h+var_140]; char **
0x100404417  mov     [rsp+168h+var_148], 104h
0x100404420  mov     ecx, ebx; unsigned int
0x100404422  call    ?XE_FormatModuleAndOffsetFromAddress@@YAJIPEBXPEAPEADPEA_K@Z; XE_FormatModuleAndOffsetFromAddress(uint,void const *,char * *,unsigned __int64 *)
0x100404427  cmp     [rsp+168h+var_148], 104h
0x100404430  jz      short loc_100404474
0x100404432  mov     rax, cs:__imp_?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x100404439  mov     r8, [rax]
0x10040443c  test    r8, r8
0x10040443f  jnz     short loc_10040444B
0x100404441  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100404448  mov     r8, [rax]
0x10040444b  lea     rdx, [rsp+168h+var_138]
0x100404450  lea     rcx, aHs_0; "%hs"
0x100404457  call    r8
0x10040445a  test    rsi, rsi
0x10040445d  jz      short loc_100404474
0x10040445f  lea     r8, [rsp+168h+var_138]
0x100404464  mov     rcx, rsi
0x100404467  lea     rdx, aFrame; "Frame"
0x10040446e  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x100404474  inc     ebx
0x100404476  add     rdi, 8
0x10040447a  cmp     ebx, ebp
0x10040447c  jb      short loc_100404400
0x10040447e  test    rsi, rsi
0x100404481  jz      short loc_10040448C
0x100404483  mov     rcx, rsi
0x100404486  call    cs:__imp_?Flush@CDStream@@QEAAHXZ; CDStream::Flush(void)
0x10040448c  mov     rcx, [rsp+168h+var_28]
0x100404494  xor     rcx, rsp; StackCookie
0x100404497  call    __security_check_cookie
0x10040449c  mov     rbx, [rsp+168h+arg_8]
0x1004044a4  add     rsp, 150h
0x1004044ab  pop     rdi
0x1004044ac  pop     rsi
0x1004044ad  pop     rbp
0x1004044ae  retn
```
