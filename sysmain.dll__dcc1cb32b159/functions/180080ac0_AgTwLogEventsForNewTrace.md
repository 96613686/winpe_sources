# AgTwLogEventsForNewTrace

- ea: `0x180080ac0`
- end: `0x180080be5`
- name: `AgTwLogEventsForNewTrace`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080bec`
- `0x180080e20`

## callees

- `0x180057a3c`
- `0x180080ac0`
- `0x1800b645a`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180080b1b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180080b1b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180080b81`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180080b81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080bd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080bd2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080b3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080b3e`

## pseudocode

```c
__int64 __fastcall AgTwLogEventsForNewTrace(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rcx
  unsigned int v5; // ebx
  void *v6; // rsi
  DWORD LengthSid; // ebp
  SIZE_T v8; // rbx
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v14; // [rsp+20h] [rbp-48h] BYREF
  __int64 (__fastcall *v15)(); // [rsp+28h] [rbp-40h]
  __int64 (__fastcall *v16)(); // [rsp+30h] [rbp-38h]

  v3 = *(_QWORD *)(a1 + 24);
  v15 = PfTrTraceAddEvent;
  v14 = a2;
  v16 = AgTwGetEventTime;
  PfPrLogUserActiveEvent(v3, &v14);
  if ( *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1872LL) == -1 )
  {
    return 1245;
  }
  else
  {
    v6 = *(void **)(*(_QWORD *)&PfSvcGlobals + 1880LL);
    LengthSid = GetLengthSid(v6);
    v8 = (LengthSid + 39) & 0xFFFFFFF0;
    v9 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, v8);
      v10[4] = 5;
      v10[5] = *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1872LL);
      CopySid(LengthSid, v10 + 6, v6);
      v11 = v14;
      v12 = *(_QWORD *)v10 & 0xFFFFFFFFFFFF1000uLL | 3;
      v10[2] = a3;
      *(_QWORD *)v10 = (v8 >> 2) & 0xFFC ^ v12 | 0x31000;
      v5 = ((__int64 (__fastcall *)(__int64, _DWORD *))v15)(v11, v10);
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
    }
    else
    {
      return 8;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180080ac0  mov     r11, rsp
0x180080ac3  push    rbx
0x180080ac4  push    rbp
0x180080ac5  push    rsi
0x180080ac6  push    rdi
0x180080ac7  push    r14
0x180080ac9  sub     rsp, 40h
0x180080acd  mov     rcx, [rcx+18h]
0x180080ad1  lea     rax, PfTrTraceAddEvent
0x180080ad8  mov     [r11-40h], rax
0x180080adc  mov     r14d, r8d
0x180080adf  lea     rax, AgTwGetEventTime
0x180080ae6  mov     [r11-48h], rdx
0x180080aea  lea     rdx, [r11-48h]
0x180080aee  mov     [r11-38h], rax
0x180080af2  call    PfPrLogUserActiveEvent
0x180080af7  mov     rax, cs:PfSvcGlobals
0x180080afe  cmp     dword ptr [rax+750h], 0FFFFFFFFh
0x180080b05  jnz     short loc_180080B11
0x180080b07  mov     ebx, 4DDh
0x180080b0c  jmp     loc_180080BD8
0x180080b11  mov     rsi, [rax+758h]
0x180080b18  mov     rcx, rsi; pSid
0x180080b1b  call    cs:__imp_GetLengthSid
0x180080b21  mov     rcx, cs:PfSvcGlobals
0x180080b28  xor     edx, edx; dwFlags
0x180080b2a  mov     ebp, eax
0x180080b2c  lea     ebx, [rax+27h]
0x180080b2f  mov     eax, 0FFFFFFF0h
0x180080b34  mov     rcx, [rcx+58h]; hHeap
0x180080b38  and     rbx, rax
0x180080b3b  mov     r8, rbx; dwBytes
0x180080b3e  call    cs:__imp_HeapAlloc
0x180080b44  mov     rdi, rax
0x180080b47  test    rax, rax
0x180080b4a  jnz     short loc_180080B54
0x180080b4c  lea     ebx, [rax+8]
0x180080b4f  jmp     loc_180080BD8
0x180080b54  mov     r8, rbx; Size
0x180080b57  xor     edx, edx; Val
0x180080b59  mov     rcx, rdi; void *
0x180080b5c  call    memset_0
0x180080b61  mov     dword ptr [rdi+10h], 5
0x180080b68  lea     rdx, [rdi+18h]; pDestinationSid
0x180080b6c  mov     rax, cs:PfSvcGlobals
0x180080b73  mov     r8, rsi; pSourceSid
0x180080b76  mov     ecx, [rax+750h]
0x180080b7c  mov     [rdi+14h], ecx
0x180080b7f  mov     ecx, ebp; nDestinationSidLength
0x180080b81  call    cs:__imp_CopySid
0x180080b87  mov     rax, [rdi]
0x180080b8a  mov     rdx, rdi
0x180080b8d  mov     rcx, [rsp+68h+var_48]
0x180080b92  and     rax, 0FFFFFFFFFFFF1003h
0x180080b98  or      rax, 3
0x180080b9c  shr     rbx, 2
0x180080ba0  and     ebx, 0FFCh
0x180080ba6  mov     [rdi+8], r14d
0x180080baa  xor     rax, rbx
0x180080bad  or      rax, 31000h
0x180080bb3  mov     [rdi], rax
0x180080bb6  mov     rax, [rsp+68h+var_40]
0x180080bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080bc0  mov     rcx, cs:PfSvcGlobals
0x180080bc7  mov     r8, rdi; lpMem
0x180080bca  xor     edx, edx; dwFlags
0x180080bcc  mov     ebx, eax
0x180080bce  mov     rcx, [rcx+58h]; hHeap
0x180080bd2  call    cs:__imp_HeapFree
0x180080bd8  mov     eax, ebx
0x180080bda  add     rsp, 40h
0x180080bde  pop     r14
0x180080be0  pop     rdi
0x180080be1  pop     rsi
0x180080be2  pop     rbp
0x180080be3  pop     rbx
0x180080be4  retn
```
