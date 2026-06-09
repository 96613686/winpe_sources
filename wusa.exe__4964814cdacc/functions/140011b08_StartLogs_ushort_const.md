# StartLogs(ushort const *)

- ea: `0x140011b08`
- end: `0x140011c07`
- name: `?StartLogs@@YAJPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x14001181c`
- `0x140011b08`
- `0x140013490`

## import_xrefs

- `ServicingCommon!SczFree` at `0x140011bec`
- `ServicingCommon!SczFree` at `0x140011bec`
- `ServicingCommon!SczAllocConcatSz` at `0x140011b5e`
- `ServicingCommon!SczAllocConcatSz` at `0x140011b5e`
- `ServicingCommon!SczAllocFromSz` at `0x140011b37`
- `ServicingCommon!SczAllocFromSz` at `0x140011b37`

## string_xrefs

- `0x140011ba6`: `Failed adding log file name extension: %S`

## pseudocode

```c
__int64 __fastcall StartLogs(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  int v3; // edi
  unsigned __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int16 *v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  v2 = 0;
  while ( 1 )
  {
    v3 = SczAllocFromSz(&v8, a1);
    if ( v3 < 0 )
      break;
    v4 = 48 * v2;
    if ( *(&vrgTraceLoggers + 6 * v2 + 2) )
    {
      v3 = SczAllocConcatSz(&v8);
      if ( v3 < 0 )
      {
        WusaLogDebugEventA(
          L"StartLogs",
          186,
          "Failed adding log file name extension: %S",
          *(struct TRACE_LOGGER near **)((char *)&vrgTraceLoggers + v4 + 16));
        goto LABEL_11;
      }
    }
    v3 = BeginTracing(
           v8,
           *(const unsigned __int16 **)((char *)&vrgTraceLoggers + v4),
           (const struct _GUID *)&qword_140020278[v4 / 8],
           *(_DWORD *)((char *)&vrgTraceLoggers + v4 + 40),
           (unsigned __int64 *)&qword_140020268[v4 / 8]);
    if ( v3 < 0 )
    {
      WusaLogDebugEventA(L"StartLogs", 190, "Failed enabling tracing to file: %S", v8);
      goto LABEL_11;
    }
    if ( (unsigned __int64)++v2 >= 2 )
      goto LABEL_11;
  }
  WusaLogDebugEventA(L"StartLogs", 181, "Failed allocating log file name: %S", a1);
LABEL_11:
  if ( v8 )
    SczFree(v8, v5, v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140011b08  mov     [rsp+arg_0], rbx
0x140011b0d  mov     [rsp+arg_10], rbp
0x140011b12  push    rsi
0x140011b13  push    rdi
0x140011b14  push    r14
0x140011b16  sub     rsp, 30h
0x140011b1a  mov     rbp, rcx
0x140011b1d  mov     [rsp+48h+arg_8], 0
0x140011b26  xor     ebx, ebx
0x140011b28  lea     r14, ?vrgTraceLoggers@@3PAUTRACE_LOGGER@@A; TRACE_LOGGER near * vrgTraceLoggers
0x140011b2f  mov     rdx, rbp
0x140011b32  lea     rcx, [rsp+48h+arg_8]
0x140011b37  call    cs:__imp_SczAllocFromSz
0x140011b3d  mov     edi, eax
0x140011b3f  test    eax, eax
0x140011b41  js      loc_140011BC7
0x140011b47  lea     rsi, [rbx+rbx*2]
0x140011b4b  shl     rsi, 4
0x140011b4f  mov     rdx, [rsi+r14+10h]
0x140011b54  test    rdx, rdx
0x140011b57  jz      short loc_140011B6A
0x140011b59  lea     rcx, [rsp+48h+arg_8]
0x140011b5e  call    cs:__imp_SczAllocConcatSz
0x140011b64  mov     edi, eax
0x140011b66  test    eax, eax
0x140011b68  js      short loc_140011BA1
0x140011b6a  mov     r9d, [rsi+r14+28h]; unsigned int
0x140011b6f  lea     rax, [r14+8]
0x140011b73  mov     rdx, [rsi+r14]; unsigned __int16 *
0x140011b77  lea     r8, [r14+18h]
0x140011b7b  mov     rcx, [rsp+48h+arg_8]; unsigned __int16 *
0x140011b80  add     rax, rsi
0x140011b83  add     r8, rsi; struct _GUID *
0x140011b86  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x140011b8b  call    ?BeginTracing@@YAJPEBG0PEBU_GUID@@KPEA_K@Z; BeginTracing(ushort const *,ushort const *,_GUID const *,ulong,unsigned __int64 *)
0x140011b90  mov     edi, eax
0x140011b92  test    eax, eax
0x140011b94  js      short loc_140011BB4
0x140011b96  inc     rbx
0x140011b99  cmp     rbx, 2
0x140011b9d  jb      short loc_140011B2F
0x140011b9f  jmp     short loc_140011BE2
0x140011ba1  mov     r9, [rsi+r14+10h]
0x140011ba6  lea     r8, aFailedAddingLo; "Failed adding log file name extension: "...
0x140011bad  mov     edx, 0BAh
0x140011bb2  jmp     short loc_140011BD6
0x140011bb4  mov     r9, [rsp+48h+arg_8]
0x140011bb9  lea     r8, aFailedEnabling; "Failed enabling tracing to file: %S"
0x140011bc0  mov     edx, 0BEh
0x140011bc5  jmp     short loc_140011BD6
0x140011bc7  mov     r9, rbp
0x140011bca  lea     r8, aFailedAllocati; "Failed allocating log file name: %S"
0x140011bd1  mov     edx, 0B5h
0x140011bd6  lea     rcx, aStartlogs; "StartLogs"
0x140011bdd  call    WusaLogDebugEventA
0x140011be2  mov     rcx, [rsp+48h+arg_8]
0x140011be7  test    rcx, rcx
0x140011bea  jz      short loc_140011BF2
0x140011bec  call    cs:__imp_SczFree
0x140011bf2  mov     rbx, [rsp+48h+arg_0]
0x140011bf7  mov     eax, edi
0x140011bf9  mov     rbp, [rsp+48h+arg_10]
0x140011bfe  add     rsp, 30h
0x140011c02  pop     r14
0x140011c04  pop     rdi
0x140011c05  pop     rsi
0x140011c06  retn
```
