# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)

- ea: `0x180013af0`
- end: `0x180013da5`
- name: `?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z`
- size: `693`
- prototype: ``
- caller_count: `32`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002a70`
- `0x18000cd10`
- `0x180011de0`
- `0x1800131e0`
- `0x1800135f0`
- `0x1800143e0`
- `0x18001f2c0`
- `0x1800278b0`
- `0x1800293fc`
- `0x18002a2b4`
- `0x18002aa40`
- `0x18002ae38`
- `0x18002bdb4`
- `0x18002cc78`
- `0x18002d248`
- `0x18002d3dc`
- `0x180030950`
- `0x18003e5d8`
- `0x18003ef00`
- `0x18003f5f4`
- `0x180040760`
- `0x18004b1fc`
- `0x18004b524`
- `0x180055574`
- `0x18005749c`
- `0x1800587a0`
- `0x180058ab4`
- `0x18005ae60`
- `0x18005e078`
- `0x18005f8cc`
- `0x180060008`
- `0x180063d20`

## callees

- `0x18000dffc`
- `0x180013af0`
- `0x18001c2c8`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180013c46`
- `ntdll!RtlPopFrame` at `0x180013c46`
- `ntdll!RtlPushFrame` at `0x180013b59`
- `ntdll!RtlPushFrame` at `0x180013b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013c6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013c6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d40`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(__int64 a1, const void *a2, size_t a3)
{
  size_t v6; // r14
  size_t v7; // rax
  _WORD *v8; // r14
  size_t v9; // rdi
  size_t v10; // rdi
  unsigned int v11; // ebx
  unsigned int (__fastcall **v13)(__int64, __int64, void **); // rax
  const void *v14; // rdx
  char *v15; // r15
  size_t v16; // rdi
  size_t v17; // rdi
  __int64 v18; // rdi
  DWORD LastError; // eax
  void *v20; // [rsp+20h] [rbp-88h] BYREF
  int v21; // [rsp+28h] [rbp-80h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+30h] [rbp-78h] BYREF
  __int64 v23; // [rsp+48h] [rbp-60h]
  int v24; // [rsp+50h] [rbp-58h]
  unsigned int *v25; // [rsp+58h] [rbp-50h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`2'::__stc;
  v23 = 544438355;
  Frame.Previous = 0;
  v24 = 210;
  v25 = (unsigned int *)&v21;
  v21 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *(_DWORD *)(a1 + 8) )
  {
    SetLastError(0x54Fu);
    *v25 = 0;
    goto LABEL_11;
  }
  SetLastError(0);
  v6 = a3 + 1;
  if ( a3 + 1 > *(_QWORD *)(a1 + 24) )
  {
    SetLastError(0);
    if ( v6 > *(_QWORD *)(a1 + 24) )
    {
      v13 = *(unsigned int (__fastcall ***)(__int64, __int64, void **))a1;
      v20 = 0;
      if ( !(*v13)(a1, a3 + 1, &v20) )
      {
        *v25 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`41'::__callsite);
        goto LABEL_11;
      }
      if ( a3 != -1 )
      {
        v14 = *(const void **)(a1 + 16);
        v15 = (char *)v20;
        if ( v14 )
        {
          v16 = *(_QWORD *)(a1 + 32);
          if ( v16 >= v6 )
            v16 = a3;
          v17 = 2 * v16;
          memcpy_0(v20, v14, v17);
          *(_WORD *)&v15[v17] = 0;
        }
        else
        {
          *(_WORD *)v20 = 0;
        }
      }
      v18 = *(_QWORD *)(a1 + 16);
      if ( v18 && v18 != (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v18);
      *(_QWORD *)(a1 + 16) = v20;
      *(_QWORD *)(a1 + 24) = v6;
    }
  }
  SetLastError(0);
  v7 = *(_QWORD *)(a1 + 24);
  if ( v7 )
  {
    v8 = *(_WORD **)(a1 + 16);
    if ( a2 )
    {
      if ( a3 >= v7 )
        v9 = v7 - 1;
      else
        v9 = a3;
      v10 = v9;
      memcpy_0(*(void **)(a1 + 16), a2, v10 * 2);
      v8[v10] = 0;
    }
    else
    {
      *v8 = 0;
    }
  }
  *(_QWORD *)(a1 + 32) = a3;
  SetLastError(0);
  *v25 = 1;
LABEL_11:
  v11 = *v25;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v11 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v11;
}

```

## disassembly

```asm
0x180013af0  mov     r11, rsp
0x180013af3  push    rbx
0x180013af4  sub     rsp, 0A0h
0x180013afb  mov     rax, cs:__security_cookie
0x180013b02  xor     rax, rsp
0x180013b05  mov     [rsp+0A8h+var_48], rax
0x180013b0a  mov     [rsp+0A8h+Frame.Flags], 1
0x180013b12  lea     rax, ?__stc@?1??Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)'::`2'::__stc
0x180013b19  mov     [r11-10h], rbp
0x180013b1d  mov     rbx, rcx
0x180013b20  mov     [r11-18h], rsi
0x180013b24  lea     rcx, [r11-78h]; Frame
0x180013b28  mov     [r11-68h], rax
0x180013b2c  mov     rsi, r8
0x180013b2f  mov     [r11-28h], r12
0x180013b33  lea     rax, [r11-80h]
0x180013b37  xor     r12d, r12d
0x180013b3a  mov     qword ptr [r11-60h], 20737853h
0x180013b42  mov     [r11-70h], r12
0x180013b46  mov     rbp, rdx
0x180013b49  mov     [rsp+0A8h+var_58], 0D2h
0x180013b51  mov     [r11-50h], rax
0x180013b55  mov     [r11-80h], r12d
0x180013b59  call    cs:__imp_RtlPushFrame
0x180013b60  nop     dword ptr [rax+rax+00h]
0x180013b65  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x180013b6c  jnz     loc_180013D22
0x180013b72  cmp     [rbx+8], r12d
0x180013b76  jnz     loc_180013D3B
0x180013b7c  mov     [rsp+0A8h+var_20], rdi
0x180013b84  xor     ecx, ecx; dwErrCode
0x180013b86  mov     [rsp+0A8h+var_30], r14
0x180013b8b  call    cs:__imp_SetLastError
0x180013b92  nop     dword ptr [rax+rax+00h]
0x180013b97  lea     r14, [rsi+1]
0x180013b9b  cmp     r14, [rbx+18h]
0x180013b9f  ja      loc_180013C6B
0x180013ba5  xor     ecx, ecx; dwErrCode
0x180013ba7  call    cs:__imp_SetLastError
0x180013bae  nop     dword ptr [rax+rax+00h]
0x180013bb3  mov     rax, [rbx+18h]
0x180013bb7  test    rax, rax
0x180013bba  jz      short loc_180013BEB
0x180013bbc  mov     r14, [rbx+10h]
0x180013bc0  test    rbp, rbp
0x180013bc3  jz      loc_180013D2C
0x180013bc9  cmp     rsi, rax
0x180013bcc  jnb     loc_180013D72
0x180013bd2  mov     rdi, rsi
0x180013bd5  add     rdi, rdi
0x180013bd8  mov     rdx, rbp; Src
0x180013bdb  mov     r8, rdi; Size
0x180013bde  mov     rcx, r14; void *
0x180013be1  call    memcpy_0
0x180013be6  mov     [rdi+r14], r12w
0x180013beb  xor     ecx, ecx; dwErrCode
0x180013bed  mov     [rbx+20h], rsi
0x180013bf1  call    cs:__imp_SetLastError
0x180013bf8  nop     dword ptr [rax+rax+00h]
0x180013bfd  mov     rax, [rsp+0A8h+var_50]
0x180013c02  mov     dword ptr [rax], 1
0x180013c08  mov     rdi, [rsp+0A8h+var_20]
0x180013c10  mov     r14, [rsp+0A8h+var_30]
0x180013c15  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180013c1c  mov     rax, [rsp+0A8h+var_50]
0x180013c21  mov     r12, [rsp+0A8h+var_28]
0x180013c29  mov     rsi, [rsp+0A8h+var_18]
0x180013c31  mov     rbp, [rsp+0A8h+var_10]
0x180013c39  mov     ebx, [rax]
0x180013c3b  jnz     loc_180013D7B
0x180013c41  lea     rcx, [rsp+0A8h+Frame]; Frame
0x180013c46  call    cs:__imp_RtlPopFrame
0x180013c4d  nop     dword ptr [rax+rax+00h]
0x180013c52  mov     eax, ebx
0x180013c54  mov     rcx, [rsp+0A8h+var_48]
0x180013c59  xor     rcx, rsp; StackCookie
0x180013c5c  call    __security_check_cookie
0x180013c61  add     rsp, 0A0h
0x180013c68  pop     rbx
0x180013c69  retn
0x180013c6b  xor     ecx, ecx; dwErrCode
0x180013c6d  call    cs:__imp_SetLastError
0x180013c74  nop     dword ptr [rax+rax+00h]
0x180013c79  cmp     r14, [rbx+18h]
0x180013c7d  jbe     loc_180013BA5
0x180013c83  mov     rax, [rbx]
0x180013c86  lea     r8, [rsp+0A8h+var_88]
0x180013c8b  mov     rdx, r14
0x180013c8e  mov     [rsp+0A8h+var_88], r12
0x180013c93  mov     rcx, rbx
0x180013c96  mov     rax, [rax]
0x180013c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9e  test    eax, eax
0x180013ca0  jz      loc_180013D59
0x180013ca6  test    r14, r14
0x180013ca9  jz      short loc_180013CE1
0x180013cab  mov     rdx, [rbx+10h]; Src
0x180013caf  mov     [rsp+0A8h+var_38], r15
0x180013cb4  mov     r15, [rsp+0A8h+var_88]
0x180013cb9  test    rdx, rdx
0x180013cbc  jz      short loc_180013D35
0x180013cbe  mov     rdi, [rbx+20h]
0x180013cc2  mov     rcx, r15; void *
0x180013cc5  cmp     rdi, r14
0x180013cc8  cmovnb  rdi, rsi
0x180013ccc  add     rdi, rdi
0x180013ccf  mov     r8, rdi; Size
0x180013cd2  call    memcpy_0
0x180013cd7  mov     [rdi+r15], r12w
0x180013cdc  mov     r15, [rsp+0A8h+var_38]
0x180013ce1  mov     rdi, [rbx+10h]
0x180013ce5  test    rdi, rdi
0x180013ce8  jz      short loc_180013D10
0x180013cea  mov     rax, [rbx]
0x180013ced  mov     rcx, rbx
0x180013cf0  mov     rax, [rax+10h]
0x180013cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cf9  cmp     rdi, rax
0x180013cfc  jz      short loc_180013D10
0x180013cfe  mov     rax, [rbx]
0x180013d01  mov     rdx, rdi
0x180013d04  mov     rcx, rbx
0x180013d07  mov     rax, [rax+8]
0x180013d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d10  mov     rax, [rsp+0A8h+var_88]
0x180013d15  mov     [rbx+10h], rax
0x180013d19  mov     [rbx+18h], r14
0x180013d1d  jmp     loc_180013BA5
0x180013d22  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180013d27  jmp     loc_180013B72
0x180013d2c  mov     [r14], r12w
0x180013d30  jmp     loc_180013BEB
0x180013d35  mov     [r15], r12w
0x180013d39  jmp     short loc_180013CDC
0x180013d3b  mov     ecx, 54Fh; dwErrCode
0x180013d40  call    cs:__imp_SetLastError
0x180013d47  nop     dword ptr [rax+rax+00h]
0x180013d4c  mov     rax, [rsp+0A8h+var_50]
0x180013d51  mov     [rax], r12d
0x180013d54  jmp     loc_180013C15
0x180013d59  mov     rax, [rsp+0A8h+var_50]
0x180013d5e  lea     rcx, ?__callsite@?CJ@??Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180013d65  mov     [rax], r12d
0x180013d68  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180013d6d  jmp     loc_180013C08
0x180013d72  lea     rdi, [rax-1]
0x180013d76  jmp     loc_180013BD5
0x180013d7b  test    ebx, ebx
0x180013d7d  jz      short loc_180013D8B
0x180013d7f  xor     ecx, ecx; char *
0x180013d81  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180013d86  jmp     loc_180013C41
0x180013d8b  call    cs:__imp_GetLastError
0x180013d92  nop     dword ptr [rax+rax+00h]
0x180013d97  mov     ecx, eax; unsigned int
0x180013d99  xor     edx, edx; Format
0x180013d9b  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180013da0  jmp     loc_180013C41
```
