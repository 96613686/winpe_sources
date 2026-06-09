# SspiGetTargetHostName

- ea: `0x18000ffb0`
- end: `0x1800100aa`
- name: `SspiGetTargetHostName`
- size: `250`
- prototype: `SECURITY_STATUS __stdcall(PCWSTR pszTargetName, PWSTR *pszHostName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fae0`

## callees

- `0x180005cc0`
- `0x18000ffb0`
- `0x1800100b0`
- `0x180018600`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x180010033`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x180010033`
- `ntdll!RtlInitUnicodeString` at `0x18000ffd4`
- `ntdll!RtlInitUnicodeString` at `0x18000ffd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001000a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001007b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001000a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001007b`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiGetTargetHostName(PCWSTR pszTargetName, PWSTR *pszHostName)
{
  int TargetHostName; // eax
  NTSTATUS v4; // ebx
  WCHAR *v5; // rax
  wchar_t *v6; // rax
  WCHAR *v8; // rax
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v10; // [rsp+30h] [rbp-18h] BYREF

  v10 = 0;
  v9 = 0;
  RtlInitUnicodeString(&v10, pszTargetName);
  *pszHostName = 0;
  TargetHostName = SspiHelperGetTargetHostName(&v10, &v9);
  v4 = TargetHostName;
  if ( TargetHostName != -1073741275 )
  {
    if ( TargetHostName < 0 )
      goto LABEL_5;
    v8 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v9.Length + 2 + 2LL);
    *pszHostName = v8;
    if ( v8 )
    {
      memcpy_0(v8, v9.Buffer, v9.Length);
      goto LABEL_5;
    }
LABEL_8:
    v4 = -1073741801;
    goto LABEL_5;
  }
  v5 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v10.Length + 2 + 2LL);
  *pszHostName = v5;
  if ( !v5 )
    goto LABEL_8;
  v4 = 0;
  memcpy_0(v5, v10.Buffer, v10.Length);
  v6 = wcsrchr(*pszHostName, 0x40u);
  if ( v6 )
    *v6 = 0;
LABEL_5:
  if ( v9.Buffer )
    SspiLocalFree(v9.Buffer);
  return SspNtStatusToSecStatus(v4);
}

```

## disassembly

```asm
0x18000ffb0  mov     rax, rsp
0x18000ffb3  mov     [rax+8], rbx
0x18000ffb7  push    rsi
0x18000ffb8  sub     rsp, 40h
0x18000ffbc  mov     rsi, rdx
0x18000ffbf  xorps   xmm0, xmm0
0x18000ffc2  mov     rdx, rcx; SourceString
0x18000ffc5  xorps   xmm1, xmm1
0x18000ffc8  lea     rcx, [rax-18h]; DestinationString
0x18000ffcc  movups  xmmword ptr [rax-18h], xmm0
0x18000ffd0  movups  xmmword ptr [rax-28h], xmm1
0x18000ffd4  call    cs:__imp_RtlInitUnicodeString
0x18000ffda  lea     rdx, [rsp+48h+var_28]; struct _UNICODE_STRING *
0x18000ffdf  mov     qword ptr [rsi], 0
0x18000ffe6  lea     rcx, [rsp+48h+var_18]; struct _UNICODE_STRING *
0x18000ffeb  call    ?SspiHelperGetTargetHostName@@YAJPEAU_UNICODE_STRING@@0@Z; SspiHelperGetTargetHostName(_UNICODE_STRING *,_UNICODE_STRING *)
0x18000fff0  mov     ebx, eax
0x18000fff2  cmp     eax, 0C0000225h
0x18000fff7  jnz     short loc_180010066
0x18000fff9  movzx   edx, [rsp+48h+var_18.Length]
0x18000fffe  mov     ecx, 40h ; '@'; uFlags
0x180010003  add     edx, 2
0x180010006  add     rdx, 2; uBytes
0x18001000a  call    cs:__imp_LocalAlloc
0x180010010  mov     [rsi], rax
0x180010013  test    rax, rax
0x180010016  jz      short loc_180010058
0x180010018  movzx   r8d, [rsp+48h+var_18.Length]; Size
0x18001001e  mov     rcx, rax; void *
0x180010021  mov     rdx, [rsp+48h+var_18.Buffer]; Src
0x180010026  xor     ebx, ebx
0x180010028  call    memcpy_0
0x18001002d  mov     rcx, [rsi]; Str
0x180010030  lea     edx, [rbx+40h]; Ch
0x180010033  call    cs:__imp_wcsrchr
0x180010039  test    rax, rax
0x18001003c  jnz     short loc_18001005F
0x18001003e  cmp     [rsp+48h+var_28.Buffer], 0
0x180010044  jnz     short loc_18001009E
0x180010046  mov     ecx, ebx
0x180010048  call    SspNtStatusToSecStatus
0x18001004d  mov     rbx, [rsp+48h+arg_0]
0x180010052  add     rsp, 40h
0x180010056  pop     rsi
0x180010057  retn
0x180010058  mov     ebx, 0C0000017h
0x18001005d  jmp     short loc_18001003E
0x18001005f  xor     ecx, ecx
0x180010061  mov     [rax], cx
0x180010064  jmp     short loc_18001003E
0x180010066  test    eax, eax
0x180010068  js      short loc_18001003E
0x18001006a  movzx   edx, [rsp+48h+var_28.Length]
0x18001006f  mov     ecx, 40h ; '@'; uFlags
0x180010074  add     edx, 2
0x180010077  add     rdx, 2; uBytes
0x18001007b  call    cs:__imp_LocalAlloc
0x180010081  mov     [rsi], rax
0x180010084  test    rax, rax
0x180010087  jz      short loc_180010058
0x180010089  movzx   r8d, [rsp+48h+var_28.Length]; Size
0x18001008f  mov     rcx, rax; void *
0x180010092  mov     rdx, [rsp+48h+var_28.Buffer]; Src
0x180010097  call    memcpy_0
0x18001009c  jmp     short loc_18001003E
0x18001009e  mov     rcx, [rsp+48h+var_28.Buffer]; DataBuffer
0x1800100a3  call    SspiLocalFree
0x1800100a8  jmp     short loc_180010046
```
