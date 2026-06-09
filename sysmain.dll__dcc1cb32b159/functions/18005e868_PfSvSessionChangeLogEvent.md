# PfSvSessionChangeLogEvent

- ea: `0x18005e868`
- end: `0x18005ea74`
- name: `PfSvSessionChangeLogEvent`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004c020`

## callees

- `0x18005e868`
- `0x180069fa4`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e8d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e8d2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e93d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e93d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ea4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ea4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e8fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e8fd`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18005e9f5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18005e9f5`

## pseudocode

```c
__int64 __fastcall PfSvSessionChangeLogEvent(int a1, PSID *a2, int a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  DWORD LengthSid; // eax
  DWORD v8; // r15d
  SIZE_T v9; // r12
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdi
  TRACEHANDLE v15; // rcx
  unsigned int v16; // eax
  __int128 v19; // [rsp+28h] [rbp-51h] BYREF
  _DWORD *v20; // [rsp+38h] [rbp-41h]
  struct _EVENT_TRACE_HEADER EventTrace; // [rsp+40h] [rbp-39h] BYREF
  char *v22; // [rsp+70h] [rbp-9h]
  int v23; // [rsp+78h] [rbp-1h]

  v3 = *(_QWORD *)&PfSvcGlobals;
  v20 = 0;
  v19 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 460LL) & 0x40) != 0
    || (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x100) != 0 )
  {
    v6 = 0;
    if ( a2 )
    {
      LengthSid = GetLengthSid(*a2);
      v3 = *(_QWORD *)&PfSvcGlobals;
      v8 = LengthSid;
    }
    else
    {
      v8 = 12;
    }
    v9 = (v8 + 39) & 0xFFFFFFF0;
    v10 = HeapAlloc(*(HANDLE *)(v3 + 88), 0, v9);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, (v8 + 39) & 0xFFFFFFF0);
      v11[4] = a1;
      v11[5] = a3;
      if ( a2 )
        CopySid(v8, v11 + 6, *a2);
      *(_QWORD *)v11 = (v9 >> 2) & 0xFFC ^ (*(_QWORD *)v11 & 0xFFFFFFFFFFFF1000uLL | 3) | 0x11000;
      v12 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      v13 = *(_QWORD *)&PfSvcGlobals;
      *(_QWORD *)v11 |= 0x20000uLL;
      v11[2] = (v12 >> 10) + *(_DWORD *)(v13 + 240);
      v14 = *(_QWORD *)&PfSvcGlobals;
      if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 460LL) & 0x40) != 0 )
      {
        memset_0(&EventTrace, 0, 0x40u);
        v15 = *(_QWORD *)(v14 + 448);
        EventTrace.GuidPtr = (ULONGLONG)PfLgEventGuid;
        EventTrace.Size = 64;
        v23 = v9 - 16;
        EventTrace.UserTime = 1703936;
        EventTrace.Class.Type = 22;
        v22 = (char *)(v11 + 4);
        TraceEvent(v15, &EventTrace);
        v14 = *(_QWORD *)&PfSvcGlobals;
      }
      if ( (*(_DWORD *)(v14 + 244) & 0x100) != 0 )
      {
        v19 = 0x400000000001uLL;
        v20 = v11;
        v16 = PfSvServiceCommandSend(v14 + 1616, &v19, 24);
        v14 = *(_QWORD *)&PfSvcGlobals;
        v6 = v16;
      }
      HeapFree(*(HANDLE *)(v14 + 88), 0, v11);
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18005e868  push    rbp
0x18005e86a  push    rbx
0x18005e86b  push    rsi
0x18005e86c  push    rdi
0x18005e86d  push    r12
0x18005e86f  push    r13
0x18005e871  push    r14
0x18005e873  push    r15
0x18005e875  lea     rbp, [rsp-1Fh]
0x18005e87a  sub     rsp, 98h
0x18005e881  mov     rax, cs:__security_cookie
0x18005e888  xor     rax, rsp
0x18005e88b  mov     [rbp+57h+var_50], rax
0x18005e88f  xor     eax, eax
0x18005e891  mov     [rbp+57h+var_B0], ecx
0x18005e894  mov     rcx, cs:PfSvcGlobals
0x18005e89b  xorps   xmm0, xmm0
0x18005e89e  mov     r13d, r8d
0x18005e8a1  mov     [rbp+57h+var_98], rax
0x18005e8a5  mov     rdi, rdx
0x18005e8a8  movups  [rbp+57h+var_A8], xmm0
0x18005e8ac  test    byte ptr [rcx+1CCh], 40h
0x18005e8b3  jnz     short loc_18005E8C8
0x18005e8b5  test    dword ptr [rcx+0F4h], 100h
0x18005e8bf  jnz     short loc_18005E8C8
0x18005e8c1  xor     ebx, ebx
0x18005e8c3  jmp     loc_18005EA52
0x18005e8c8  xor     ebx, ebx
0x18005e8ca  test    rdi, rdi
0x18005e8cd  jz      short loc_18005E8E4
0x18005e8cf  mov     rcx, [rdx]; pSid
0x18005e8d2  call    cs:__imp_GetLengthSid
0x18005e8d8  mov     rcx, cs:PfSvcGlobals
0x18005e8df  mov     r15d, eax
0x18005e8e2  jmp     short loc_18005E8EA
0x18005e8e4  mov     r15d, 0Ch
0x18005e8ea  mov     rcx, [rcx+58h]; hHeap
0x18005e8ee  lea     eax, [r15+27h]
0x18005e8f2  and     eax, 0FFFFFFF0h
0x18005e8f5  xor     edx, edx; dwFlags
0x18005e8f7  mov     r8d, eax; dwBytes
0x18005e8fa  mov     r12d, eax
0x18005e8fd  call    cs:__imp_HeapAlloc
0x18005e903  mov     rsi, rax
0x18005e906  test    rax, rax
0x18005e909  jnz     short loc_18005E913
0x18005e90b  lea     ebx, [rax+8]
0x18005e90e  jmp     loc_18005EA52
0x18005e913  mov     r8, r12; Size
0x18005e916  xor     edx, edx; Val
0x18005e918  mov     rcx, rsi; void *
0x18005e91b  call    memset_0
0x18005e920  mov     eax, [rbp+57h+var_B0]
0x18005e923  lea     r14, [rsi+10h]
0x18005e927  mov     [r14], eax
0x18005e92a  mov     [r14+4], r13d
0x18005e92e  test    rdi, rdi
0x18005e931  jz      short loc_18005E943
0x18005e933  mov     r8, [rdi]; pSourceSid
0x18005e936  lea     rdx, [r14+8]; pDestinationSid
0x18005e93a  mov     ecx, r15d; nDestinationSidLength
0x18005e93d  call    cs:__imp_CopySid
0x18005e943  mov     rcx, [rsi]
0x18005e946  mov     rax, r12
0x18005e949  shr     rax, 2
0x18005e94d  and     rcx, 0FFFFFFFFFFFF1003h
0x18005e954  and     eax, 0FFCh
0x18005e959  or      rcx, 3
0x18005e95d  xor     rcx, rax
0x18005e960  mov     r15d, 40h ; '@'
0x18005e966  or      rcx, 11000h
0x18005e96d  mov     eax, 7FFE0320h
0x18005e972  mov     [rsi], rcx
0x18005e975  mov     ecx, ds:7FFE0004h
0x18005e97c  shl     rcx, 20h
0x18005e980  mov     rax, [rax]
0x18005e983  shl     rax, 8
0x18005e987  mul     rcx
0x18005e98a  mov     rax, cs:PfSvcGlobals
0x18005e991  bts     qword ptr [rsi], 11h
0x18005e996  shr     rdx, 0Ah
0x18005e99a  mov     eax, [rax+0F0h]
0x18005e9a0  add     eax, edx
0x18005e9a2  mov     [rsi+8], eax
0x18005e9a5  mov     rdi, cs:PfSvcGlobals
0x18005e9ac  test    [rdi+1CCh], r15b
0x18005e9b3  jz      short loc_18005EA02
0x18005e9b5  mov     r8d, r15d; Size
0x18005e9b8  lea     rcx, [rbp+57h+EventTrace]; void *
0x18005e9bc  xor     edx, edx; Val
0x18005e9be  call    memset_0
0x18005e9c3  mov     rcx, [rdi+1C0h]; TraceHandle
0x18005e9ca  lea     rax, PfLgEventGuid
0x18005e9d1  mov     qword ptr [rbp+57h+EventTrace.18h], rax
0x18005e9d5  lea     rdx, [rbp+57h+EventTrace]; EventTrace
0x18005e9d9  lea     eax, [r12-10h]
0x18005e9de  mov     [rbp+57h+EventTrace.Size], r15w
0x18005e9e3  mov     [rbp+57h+var_58], eax
0x18005e9e6  mov     dword ptr [rbp+57h+EventTrace.28h+4], 1A0000h
0x18005e9ed  mov     byte ptr [rbp+57h+EventTrace.4], 16h
0x18005e9f1  mov     [rbp+57h+var_60], r14
0x18005e9f5  call    cs:__imp_TraceEvent
0x18005e9fb  mov     rdi, cs:PfSvcGlobals
0x18005ea02  test    dword ptr [rdi+0F4h], 100h
0x18005ea0c  jz      short loc_18005EA43
0x18005ea0e  lea     rcx, [rdi+650h]
0x18005ea15  mov     qword ptr [rbp+57h+var_A8+8], rbx
0x18005ea19  mov     r8d, 18h
0x18005ea1f  mov     dword ptr [rbp+57h+var_A8], 1
0x18005ea26  lea     rdx, [rbp+57h+var_A8]
0x18005ea2a  mov     dword ptr [rbp+57h+var_A8+4], 4000h
0x18005ea31  mov     [rbp+57h+var_98], rsi
0x18005ea35  call    PfSvServiceCommandSend
0x18005ea3a  mov     rdi, cs:PfSvcGlobals
0x18005ea41  mov     ebx, eax
0x18005ea43  mov     rcx, [rdi+58h]; hHeap
0x18005ea47  mov     r8, rsi; lpMem
0x18005ea4a  xor     edx, edx; dwFlags
0x18005ea4c  call    cs:__imp_HeapFree
0x18005ea52  mov     eax, ebx
0x18005ea54  mov     rcx, [rbp+57h+var_50]
0x18005ea58  xor     rcx, rsp; StackCookie
0x18005ea5b  call    __security_check_cookie
0x18005ea60  add     rsp, 98h
0x18005ea67  pop     r15
0x18005ea69  pop     r14
0x18005ea6b  pop     r13
0x18005ea6d  pop     r12
0x18005ea6f  pop     rdi
0x18005ea70  pop     rsi
0x18005ea71  pop     rbx
0x18005ea72  pop     rbp
0x18005ea73  retn
```
