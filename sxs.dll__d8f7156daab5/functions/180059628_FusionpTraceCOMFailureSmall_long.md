# FusionpTraceCOMFailureSmall(long)

- ea: `0x180059628`
- end: `0x180059757`
- name: `?FusionpTraceCOMFailureSmall@@YAXJ@Z`
- size: `303`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005c140`

## callees

- `0x18000c000`
- `0x180011864`
- `0x180059628`
- `0x180059760`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x1800596c0`
- `ntdll!_snprintf_s` at `0x1800596c0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180059698`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180059698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059655`

## string_xrefs

- `0x1800596f7`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx\n`

## pseudocode

```c
void __fastcall FusionpTraceCOMFailureSmall(DWORD dwMessageId)
{
  DWORD CurrentThreadId; // edi
  DWORD v3; // [rsp+38h] [rbp-C8h]
  DWORD v4; // [rsp+40h] [rbp-C0h]
  __int128 v5; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v6; // [rsp+60h] [rbp-A0h]
  UNICODE_STRING SearchString; // [rsp+68h] [rbp-98h] BYREF
  CHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  FusionpGetProcessImageFileName(&SearchString);
  Buffer[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, dwMessageId, 0, Buffer, 0x100u, 0) )
  {
    _snprintf_s(Buffer, 0x100u, 0xFFu, "<Untranslatable(non-existed or too long) HRESULT: 0x%08lx>", dwMessageId);
    Buffer[255] = 0;
  }
  v5 = 0;
  v6 = 0;
  FusionpGetActiveFrameInfo((struct _FRAME_INFO *)&v5);
  v4 = dwMessageId;
  v3 = CurrentThreadId;
  FusionpDbgPrintEx(
    0x80000010,
    "%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx\n",
    (_QWORD)v5,
    (unsigned int)v6,
    *((_QWORD *)&v5 + 1),
    64,
    &SearchString,
    v3,
    v4,
    Buffer);
}

```

## disassembly

```asm
0x180059628  mov     [rsp-8+arg_8], rbx
0x18005962d  mov     [rsp-8+arg_10], rdi
0x180059632  push    rbp
0x180059633  lea     rbp, [rsp-90h]
0x18005963b  sub     rsp, 190h
0x180059642  mov     rax, cs:__security_cookie
0x180059649  xor     rax, rsp
0x18005964c  mov     [rbp+90h+var_10], rax
0x180059653  mov     ebx, ecx
0x180059655  call    cs:__imp_GetCurrentThreadId
0x18005965c  nop     dword ptr [rax+rax+00h]
0x180059661  lea     rcx, [rsp+190h+SearchString]; SearchString
0x180059666  mov     edi, eax
0x180059668  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x18005966d  lea     rax, [rbp+90h+Buffer]
0x180059671  mov     [rsp+190h+Arguments], 0; Arguments
0x18005967a  mov     [rsp+190h+nSize], 100h; nSize
0x180059682  xor     r9d, r9d; dwLanguageId
0x180059685  mov     r8d, ebx; dwMessageId
0x180059688  mov     [rsp+190h+lpBuffer], rax; lpBuffer
0x18005968d  xor     edx, edx; lpSource
0x18005968f  mov     [rbp+90h+Buffer], 0
0x180059693  mov     ecx, 10FFh; dwFlags
0x180059698  call    cs:__imp_FormatMessageA
0x18005969f  nop     dword ptr [rax+rax+00h]
0x1800596a4  test    eax, eax
0x1800596a6  jnz     short loc_1800596D0
0x1800596a8  mov     edx, 100h; BufferCount
0x1800596ad  mov     dword ptr [rsp+190h+lpBuffer], ebx
0x1800596b1  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x1800596b8  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800596bc  lea     r8d, [rdx-1]; MaxCount
0x1800596c0  call    cs:__imp__snprintf_s
0x1800596c7  nop     dword ptr [rax+rax+00h]
0x1800596cc  mov     [rbp+90h+var_11], 0
0x1800596d0  xorps   xmm0, xmm0
0x1800596d3  lea     rcx, [rsp+190h+var_140]; struct _FRAME_INFO *
0x1800596d8  xor     eax, eax
0x1800596da  movups  [rsp+190h+var_140], xmm0
0x1800596df  mov     [rsp+190h+var_130], rax
0x1800596e4  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x1800596e9  mov     r9d, dword ptr [rsp+190h+var_130]
0x1800596ee  lea     rax, [rbp+90h+Buffer]
0x1800596f2  mov     r8, qword ptr [rsp+190h+var_140]
0x1800596f7  lea     rdx, aSDFunctionSIub_0; "%s(%d): [function %s %Iubit process %wZ"...
0x1800596fe  mov     [rsp+190h+var_148], rax
0x180059703  mov     ecx, 80000010h; unsigned int
0x180059708  mov     [rsp+190h+var_150], ebx
0x18005970c  lea     rax, [rsp+190h+SearchString]
0x180059711  mov     [rsp+190h+var_158], edi
0x180059715  mov     [rsp+190h+Arguments], rax
0x18005971a  mov     rax, qword ptr [rsp+190h+var_140+8]
0x18005971f  mov     qword ptr [rsp+190h+nSize], 40h ; '@'
0x180059728  mov     [rsp+190h+lpBuffer], rax
0x18005972d  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180059732  mov     rcx, [rbp+90h+var_10]
0x180059739  xor     rcx, rsp; StackCookie
0x18005973c  call    __security_check_cookie
0x180059741  lea     r11, [rsp+190h+var_s0]
0x180059749  mov     rbx, [r11+18h]
0x18005974d  mov     rdi, [r11+20h]
0x180059751  mov     rsp, r11
0x180059754  pop     rbp
0x180059755  retn
```
