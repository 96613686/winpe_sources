# FusionpTraceCallCOMSuccessfulExitSmall(long)

- ea: `0x1800671dc`
- end: `0x18006730b`
- name: `?FusionpTraceCallCOMSuccessfulExitSmall@@YAXJ@Z`
- size: `303`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067170`

## callees

- `0x18000c000`
- `0x180011864`
- `0x180059760`
- `0x1800671dc`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x180067274`
- `ntdll!_snprintf_s` at `0x180067274`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18006724c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18006724c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067209`

## string_xrefs

- `0x1800672ab`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx\n`

## pseudocode

```c
void __fastcall FusionpTraceCallCOMSuccessfulExitSmall(DWORD dwMessageId)
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
    0x80000008,
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
0x1800671dc  mov     [rsp-8+arg_8], rbx
0x1800671e1  mov     [rsp-8+arg_10], rdi
0x1800671e6  push    rbp
0x1800671e7  lea     rbp, [rsp-90h]
0x1800671ef  sub     rsp, 190h
0x1800671f6  mov     rax, cs:__security_cookie
0x1800671fd  xor     rax, rsp
0x180067200  mov     [rbp+90h+var_10], rax
0x180067207  mov     ebx, ecx
0x180067209  call    cs:__imp_GetCurrentThreadId
0x180067210  nop     dword ptr [rax+rax+00h]
0x180067215  lea     rcx, [rsp+190h+SearchString]; SearchString
0x18006721a  mov     edi, eax
0x18006721c  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x180067221  lea     rax, [rbp+90h+Buffer]
0x180067225  mov     [rsp+190h+Arguments], 0; Arguments
0x18006722e  mov     [rsp+190h+nSize], 100h; nSize
0x180067236  xor     r9d, r9d; dwLanguageId
0x180067239  mov     r8d, ebx; dwMessageId
0x18006723c  mov     [rsp+190h+lpBuffer], rax; lpBuffer
0x180067241  xor     edx, edx; lpSource
0x180067243  mov     [rbp+90h+Buffer], 0
0x180067247  mov     ecx, 10FFh; dwFlags
0x18006724c  call    cs:__imp_FormatMessageA
0x180067253  nop     dword ptr [rax+rax+00h]
0x180067258  test    eax, eax
0x18006725a  jnz     short loc_180067284
0x18006725c  mov     edx, 100h; BufferCount
0x180067261  mov     dword ptr [rsp+190h+lpBuffer], ebx
0x180067265  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x18006726c  lea     rcx, [rbp+90h+Buffer]; Buffer
0x180067270  lea     r8d, [rdx-1]; MaxCount
0x180067274  call    cs:__imp__snprintf_s
0x18006727b  nop     dword ptr [rax+rax+00h]
0x180067280  mov     [rbp+90h+var_11], 0
0x180067284  xorps   xmm0, xmm0
0x180067287  lea     rcx, [rsp+190h+var_140]; struct _FRAME_INFO *
0x18006728c  xor     eax, eax
0x18006728e  movups  [rsp+190h+var_140], xmm0
0x180067293  mov     [rsp+190h+var_130], rax
0x180067298  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x18006729d  mov     r9d, dword ptr [rsp+190h+var_130]
0x1800672a2  lea     rax, [rbp+90h+Buffer]
0x1800672a6  mov     r8, qword ptr [rsp+190h+var_140]
0x1800672ab  lea     rdx, aSDFunctionSIub_0; "%s(%d): [function %s %Iubit process %wZ"...
0x1800672b2  mov     [rsp+190h+var_148], rax
0x1800672b7  mov     ecx, 80000008h; unsigned int
0x1800672bc  mov     [rsp+190h+var_150], ebx
0x1800672c0  lea     rax, [rsp+190h+SearchString]
0x1800672c5  mov     [rsp+190h+var_158], edi
0x1800672c9  mov     [rsp+190h+Arguments], rax
0x1800672ce  mov     rax, qword ptr [rsp+190h+var_140+8]
0x1800672d3  mov     qword ptr [rsp+190h+nSize], 40h ; '@'
0x1800672dc  mov     [rsp+190h+lpBuffer], rax
0x1800672e1  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800672e6  mov     rcx, [rbp+90h+var_10]
0x1800672ed  xor     rcx, rsp; StackCookie
0x1800672f0  call    __security_check_cookie
0x1800672f5  lea     r11, [rsp+190h+var_s0]
0x1800672fd  mov     rbx, [r11+18h]
0x180067301  mov     rdi, [r11+20h]
0x180067305  mov     rsp, r11
0x180067308  pop     rbp
0x180067309  retn
```
