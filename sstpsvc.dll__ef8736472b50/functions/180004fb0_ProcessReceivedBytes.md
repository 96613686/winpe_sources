# ProcessReceivedBytes

- ea: `0x180004fb0`
- end: `0x180005109`
- name: `ProcessReceivedBytes`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000afb0`

## callees

- `0x180002f80`
- `0x180004fb0`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005002`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005070`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005070`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000505d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000505d`

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
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"CoId=%hs:Dropping packet since disconnect in progress", v2 + 552);
      if ( (byte_18002E903 & 8) != 0 )
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
0x180004fb0  mov     [rsp+arg_8], rbx
0x180004fb5  mov     [rsp+arg_10], rsi
0x180004fba  push    rdi
0x180004fbb  sub     rsp, 830h
0x180004fc2  mov     rax, cs:__security_cookie
0x180004fc9  xor     rax, rsp
0x180004fcc  mov     [rsp+838h+var_18], rax
0x180004fd4  mov     rdi, rcx
0x180004fd7  xor     eax, eax
0x180004fd9  lea     rcx, [rsp+838h+var_814]; void *
0x180004fde  mov     [rsp+838h+var_818], eax
0x180004fe2  xor     edx, edx; Val
0x180004fe4  mov     r8d, 7FCh; Size
0x180004fea  call    memset_0
0x180004fef  mov     rbx, [rdi+38h]
0x180004ff3  mov     qword ptr [rdi+38h], 0
0x180004ffb  lea     rcx, [rbx+120h]; lpCriticalSection
0x180005002  call    cs:__imp_EnterCriticalSection
0x180005009  nop     dword ptr [rax+rax+00h]
0x18000500e  cmp     byte ptr [rbx+1B3h], 0
0x180005015  jnz     loc_1800050A2
0x18000501b  lea     r8, [rdi+28h]
0x18000501f  mov     [rdi+30h], r8
0x180005023  lea     rdx, [rbx+1A0h]
0x18000502a  mov     [r8], r8
0x18000502d  mov     rax, [rdx+8]
0x180005031  mov     [r8], rdx
0x180005034  mov     [rdi+30h], rax
0x180005038  mov     [rax], r8
0x18000503b  mov     [rdx+8], r8
0x18000503f  cmp     byte ptr [rbx+1B0h], 0
0x180005046  jnz     short loc_180005069
0x180005048  mov     byte ptr [rbx+1B0h], 1
0x18000504f  lock inc dword ptr [rbx+0D0h]
0x180005056  mov     rcx, [rbx+150h]; pwk
0x18000505d  call    cs:__imp_SubmitThreadpoolWork
0x180005064  nop     dword ptr [rax+rax+00h]
0x180005069  lea     rcx, [rbx+120h]; lpCriticalSection
0x180005070  call    cs:__imp_LeaveCriticalSection
0x180005077  nop     dword ptr [rax+rax+00h]
0x18000507c  mov     rcx, [rsp+838h+var_18]
0x180005084  xor     rcx, rsp; StackCookie
0x180005087  call    __security_check_cookie
0x18000508c  lea     r11, [rsp+838h+var_8]
0x180005094  mov     rbx, [r11+18h]
0x180005098  mov     rsi, [r11+20h]
0x18000509c  mov     rsp, r11
0x18000509f  pop     rdi
0x1800050a0  retn
0x1800050a2  test    cs:byte_18002E903, 8
0x1800050a9  jz      short loc_1800050EB
0x1800050ab  xor     eax, eax
0x1800050ad  lea     r8, [rbx+228h]
0x1800050b4  lea     rdx, aCoidHsDropping; "CoId=%hs:Dropping packet since disconne"...
0x1800050bb  mov     word ptr [rsp+838h+var_818], ax
0x1800050c0  lea     rcx, [rsp+838h+var_818]
0x1800050c5  call    FormatRRASErrorString
0x1800050ca  test    cs:byte_18002E903, 8
0x1800050d1  jz      short loc_1800050EB
0x1800050d3  lea     r8, [rsp+838h+var_818]
0x1800050d8  lea     rdx, RasSSTPSvcTraceError
0x1800050df  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800050e6  call    McTemplateU0z_EventWriteTransfer
0x1800050eb  mov     rcx, cs:SstpSvcGlobals
0x1800050f2  mov     r8b, 1
0x1800050f5  add     rcx, 1A8h
0x1800050fc  mov     rdx, rdi
0x1800050ff  call    FreeBufferToPool
0x180005104  jmp     loc_180005069
```
