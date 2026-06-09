# FusionpTraceCOMFailureOriginationSmall(long)

- ea: `0x1800594f0`
- end: `0x18005961f`
- name: `?FusionpTraceCOMFailureOriginationSmall@@YAXJ@Z`
- size: `303`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005cdcc`

## callees

- `0x18000c000`
- `0x180011864`
- `0x1800594f0`
- `0x180059760`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x180059588`
- `ntdll!_snprintf_s` at `0x180059588`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180059560`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180059560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005951d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005951d`

## string_xrefs

- `0x1800595bf`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx\n`

## pseudocode

```c
void __fastcall FusionpTraceCOMFailureOriginationSmall(DWORD dwMessageId)
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
    0xC0000000,
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
0x1800594f0  mov     [rsp-8+arg_8], rbx
0x1800594f5  mov     [rsp-8+arg_10], rdi
0x1800594fa  push    rbp
0x1800594fb  lea     rbp, [rsp-90h]
0x180059503  sub     rsp, 190h
0x18005950a  mov     rax, cs:__security_cookie
0x180059511  xor     rax, rsp
0x180059514  mov     [rbp+90h+var_10], rax
0x18005951b  mov     ebx, ecx
0x18005951d  call    cs:__imp_GetCurrentThreadId
0x180059524  nop     dword ptr [rax+rax+00h]
0x180059529  lea     rcx, [rsp+190h+SearchString]; SearchString
0x18005952e  mov     edi, eax
0x180059530  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x180059535  lea     rax, [rbp+90h+Buffer]
0x180059539  mov     [rsp+190h+Arguments], 0; Arguments
0x180059542  mov     [rsp+190h+nSize], 100h; nSize
0x18005954a  xor     r9d, r9d; dwLanguageId
0x18005954d  mov     r8d, ebx; dwMessageId
0x180059550  mov     [rsp+190h+lpBuffer], rax; lpBuffer
0x180059555  xor     edx, edx; lpSource
0x180059557  mov     [rbp+90h+Buffer], 0
0x18005955b  mov     ecx, 10FFh; dwFlags
0x180059560  call    cs:__imp_FormatMessageA
0x180059567  nop     dword ptr [rax+rax+00h]
0x18005956c  test    eax, eax
0x18005956e  jnz     short loc_180059598
0x180059570  mov     edx, 100h; BufferCount
0x180059575  mov     dword ptr [rsp+190h+lpBuffer], ebx
0x180059579  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x180059580  lea     rcx, [rbp+90h+Buffer]; Buffer
0x180059584  lea     r8d, [rdx-1]; MaxCount
0x180059588  call    cs:__imp__snprintf_s
0x18005958f  nop     dword ptr [rax+rax+00h]
0x180059594  mov     [rbp+90h+var_11], 0
0x180059598  xorps   xmm0, xmm0
0x18005959b  lea     rcx, [rsp+190h+var_140]; struct _FRAME_INFO *
0x1800595a0  xor     eax, eax
0x1800595a2  movups  [rsp+190h+var_140], xmm0
0x1800595a7  mov     [rsp+190h+var_130], rax
0x1800595ac  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x1800595b1  mov     r9d, dword ptr [rsp+190h+var_130]
0x1800595b6  lea     rax, [rbp+90h+Buffer]
0x1800595ba  mov     r8, qword ptr [rsp+190h+var_140]
0x1800595bf  lea     rdx, aSDFunctionSIub_0; "%s(%d): [function %s %Iubit process %wZ"...
0x1800595c6  mov     [rsp+190h+var_148], rax
0x1800595cb  mov     ecx, 0C0000000h; unsigned int
0x1800595d0  mov     [rsp+190h+var_150], ebx
0x1800595d4  lea     rax, [rsp+190h+SearchString]
0x1800595d9  mov     [rsp+190h+var_158], edi
0x1800595dd  mov     [rsp+190h+Arguments], rax
0x1800595e2  mov     rax, qword ptr [rsp+190h+var_140+8]
0x1800595e7  mov     qword ptr [rsp+190h+nSize], 40h ; '@'
0x1800595f0  mov     [rsp+190h+lpBuffer], rax
0x1800595f5  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800595fa  mov     rcx, [rbp+90h+var_10]
0x180059601  xor     rcx, rsp; StackCookie
0x180059604  call    __security_check_cookie
0x180059609  lea     r11, [rsp+190h+var_s0]
0x180059611  mov     rbx, [r11+18h]
0x180059615  mov     rdi, [r11+20h]
0x180059619  mov     rsp, r11
0x18005961c  pop     rbp
0x18005961d  retn
```
