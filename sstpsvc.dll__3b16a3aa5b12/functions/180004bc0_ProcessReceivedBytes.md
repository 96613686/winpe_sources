# ProcessReceivedBytes

- ea: `0x180004bc0`
- end: `0x180004d02`
- name: `ProcessReceivedBytes`
- size: `322`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a620`

## callees

- `0x180002d70`
- `0x180004bc0`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c70`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180004c63`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180004c63`

## pseudocode

```c
void __fastcall ProcessReceivedBytes(_QWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  _QWORD *v4; // rax
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  v2 = a1[7];
  a1[7] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
  if ( *(_BYTE *)(v2 + 435) )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"CoId=%hs:Dropping packet since disconnect in progress", v2 + 552);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v5);
    }
    LOBYTE(v3) = 1;
    FreeBufferToPool((char *)SstpSvcGlobals + 424, a1, v3);
  }
  else
  {
    a1[6] = a1 + 5;
    a1[5] = a1 + 5;
    v4 = *(_QWORD **)(v2 + 424);
    a1[5] = v2 + 416;
    a1[6] = v4;
    *v4 = a1 + 5;
    *(_QWORD *)(v2 + 424) = a1 + 5;
    if ( !*(_BYTE *)(v2 + 432) )
    {
      *(_BYTE *)(v2 + 432) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 208));
      SubmitThreadpoolWork(*(PTP_WORK *)(v2 + 336));
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
}

```

## disassembly

```asm
0x180004bc0  mov     [rsp+arg_8], rbx
0x180004bc5  mov     [rsp+arg_10], rsi
0x180004bca  push    rdi
0x180004bcb  sub     rsp, 830h
0x180004bd2  mov     rax, cs:__security_cookie
0x180004bd9  xor     rax, rsp
0x180004bdc  mov     [rsp+838h+var_18], rax
0x180004be4  mov     rdi, rcx
0x180004be7  xor     eax, eax
0x180004be9  lea     rcx, [rsp+838h+var_814]; void *
0x180004bee  mov     [rsp+838h+var_818], eax
0x180004bf2  xor     edx, edx; Val
0x180004bf4  mov     r8d, 7FCh; Size
0x180004bfa  call    memset_0
0x180004bff  mov     rbx, [rdi+38h]
0x180004c03  mov     qword ptr [rdi+38h], 0
0x180004c0b  lea     rcx, [rbx+120h]; lpCriticalSection
0x180004c12  call    cs:__imp_EnterCriticalSection
0x180004c18  cmp     byte ptr [rbx+1B3h], 0
0x180004c1f  jnz     short loc_180004C9B
0x180004c21  lea     r8, [rdi+28h]
0x180004c25  mov     [rdi+30h], r8
0x180004c29  lea     rdx, [rbx+1A0h]
0x180004c30  mov     [r8], r8
0x180004c33  mov     rax, [rdx+8]
0x180004c37  mov     [r8], rdx
0x180004c3a  mov     [rdi+30h], rax
0x180004c3e  mov     [rax], r8
0x180004c41  mov     [rdx+8], r8
0x180004c45  cmp     byte ptr [rbx+1B0h], 0
0x180004c4c  jnz     short loc_180004C69
0x180004c4e  mov     byte ptr [rbx+1B0h], 1
0x180004c55  lock inc dword ptr [rbx+0D0h]
0x180004c5c  mov     rcx, [rbx+150h]; pwk
0x180004c63  call    cs:__imp_SubmitThreadpoolWork
0x180004c69  lea     rcx, [rbx+120h]; lpCriticalSection
0x180004c70  call    cs:__imp_LeaveCriticalSection
0x180004c76  mov     rcx, [rsp+838h+var_18]
0x180004c7e  xor     rcx, rsp; StackCookie
0x180004c81  call    __security_check_cookie
0x180004c86  lea     r11, [rsp+838h+var_8]
0x180004c8e  mov     rbx, [r11+18h]
0x180004c92  mov     rsi, [r11+20h]
0x180004c96  mov     rsp, r11
0x180004c99  pop     rdi
0x180004c9a  retn
0x180004c9b  test    cs:byte_18002D803, 8
0x180004ca2  jz      short loc_180004CE4
0x180004ca4  xor     eax, eax
0x180004ca6  lea     r8, [rbx+228h]
0x180004cad  lea     rdx, aCoidHsDropping; "CoId=%hs:Dropping packet since disconne"...
0x180004cb4  mov     word ptr [rsp+838h+var_818], ax
0x180004cb9  lea     rcx, [rsp+838h+var_818]
0x180004cbe  call    FormatRRASErrorString
0x180004cc3  test    cs:byte_18002D803, 8
0x180004cca  jz      short loc_180004CE4
0x180004ccc  lea     r8, [rsp+838h+var_818]
0x180004cd1  lea     rdx, RasSSTPSvcTraceError
0x180004cd8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004cdf  call    McTemplateU0z_EventWriteTransfer
0x180004ce4  mov     rcx, cs:SstpSvcGlobals
0x180004ceb  mov     r8b, 1
0x180004cee  add     rcx, 1A8h
0x180004cf5  mov     rdx, rdi
0x180004cf8  call    FreeBufferToPool
0x180004cfd  jmp     loc_180004C69
```
