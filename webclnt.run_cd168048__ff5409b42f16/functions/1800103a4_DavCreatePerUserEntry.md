# DavCreatePerUserEntry

- ea: `0x1800103a4`
- end: `0x180010470`
- name: `DavCreatePerUserEntry`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca70`
- `0x180021f00`

## callees

- `0x18000bc5c`
- `0x1800103a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001042a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001042a`
- `KERNEL32!LocalAlloc` at `0x1800103bf`
- `KERNEL32!LocalAlloc` at `0x1800103bf`

## pseudocode

```c
DWORD __fastcall DavCreatePerUserEntry(__int64 a1, _DWORD *a2, struct _RTL_CRITICAL_SECTION **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  HANDLE **v9; // rcx
  _QWORD *v10; // rdx
  HANDLE *p_OwningThread; // rax

  v6 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0x40u, 0xB0u);
  v7 = v6;
  if ( !v6 )
    return GetLastError();
  v9 = (HANDLE **)(a1 + 72);
  v10 = *(_QWORD **)(a1 + 72);
  if ( v10[1] != a1 + 72 )
    __fastfail(3u);
  v6->LockSemaphore = v9;
  p_OwningThread = &v6->OwningThread;
  *p_OwningThread = v10;
  v10[1] = p_OwningThread;
  *v9 = p_OwningThread;
  ++*(_DWORD *)(a1 + 104);
  *(_QWORD *)&v7->LockCount = a1;
  v7[1].LockCount = 1;
  LODWORD(v7[1].LockSemaphore) = 1;
  LODWORD(v7->DebugInfo) = *a2;
  HIDWORD(v7->DebugInfo) = a2[1];
  v7[4].RecursionCount = 0;
  InitializeCriticalSection(v7 + 3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v7);
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800103a4  push    rbx
0x1800103a6  push    rsi
0x1800103a7  push    rdi
0x1800103a8  push    r14
0x1800103aa  sub     rsp, 28h
0x1800103ae  mov     r14, rdx
0x1800103b1  mov     rdi, rcx
0x1800103b4  mov     edx, 0B0h; uBytes
0x1800103b9  mov     rsi, r8
0x1800103bc  lea     ecx, [rdx-70h]; uFlags
0x1800103bf  call    cs:__imp_LocalAlloc
0x1800103c5  mov     rbx, rax
0x1800103c8  test    rax, rax
0x1800103cb  jnz     short loc_1800103D8
0x1800103cd  call    cs:__imp_GetLastError
0x1800103d3  jmp     loc_180010466
0x1800103d8  lea     rcx, [rdi+48h]
0x1800103dc  mov     rdx, [rcx]
0x1800103df  cmp     [rdx+8], rcx
0x1800103e3  jz      short loc_1800103EC
0x1800103e5  mov     ecx, 3
0x1800103ea  int     29h; Win8: RtlFailFast(ecx)
0x1800103ec  mov     [rax+18h], rcx
0x1800103f0  add     rax, 10h
0x1800103f4  mov     [rax], rdx
0x1800103f7  mov     [rdx+8], rax
0x1800103fb  mov     [rcx], rax
0x1800103fe  mov     eax, 1
0x180010403  add     [rdi+68h], eax
0x180010406  lea     rcx, [rbx+78h]; lpCriticalSection
0x18001040a  mov     [rbx+8], rdi
0x18001040e  mov     [rbx+30h], eax
0x180010411  mov     [rbx+40h], eax
0x180010414  mov     eax, [r14]
0x180010417  mov     [rbx], eax
0x180010419  mov     eax, [r14+4]
0x18001041d  mov     [rbx+4], eax
0x180010420  mov     dword ptr [rbx+0ACh], 0
0x18001042a  call    cs:__imp_InitializeCriticalSection
0x180010430  mov     rcx, cs:WPP_GLOBAL_Control
0x180010437  lea     rax, WPP_GLOBAL_Control
0x18001043e  cmp     rcx, rax
0x180010441  jz      short loc_180010461
0x180010443  test    byte ptr [rcx+1Ch], 2
0x180010447  jz      short loc_180010461
0x180010449  mov     rcx, [rcx+10h]
0x18001044d  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010454  mov     edx, 97h
0x180010459  mov     r9, rbx
0x18001045c  call    WPP_SF_q
0x180010461  mov     [rsi], rbx
0x180010464  xor     eax, eax
0x180010466  add     rsp, 28h
0x18001046a  pop     r14
0x18001046c  pop     rdi
0x18001046d  pop     rsi
0x18001046e  pop     rbx
0x18001046f  retn
```
