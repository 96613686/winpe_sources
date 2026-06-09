# NotifyMakeCallComplete

- ea: `0x18000da7c`
- end: `0x18000dd62`
- name: `NotifyMakeCallComplete`
- size: `742`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002aac`
- `0x18000ebd0`

## callees

- `0x180002f50`
- `0x180005110`
- `0x180005680`
- `0x1800089dc`
- `0x180008b90`
- `0x18000da7c`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db00`

## string_xrefs

- `0x18000dcf9`: `CoId=%hs:Error completing MAKE_CALL_COMPLETE: %d`
- `0x18000dc14`: `CoId=%hs:AsyncMakeCallcomplete fails with %d`

## pseudocode

```c
char __fastcall NotifyMakeCallComplete(__int64 a1, signed int a2, _OWORD *a3)
{
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  void *v8; // rdi
  char v9; // bl
  unsigned int v10; // eax
  HANDLE v11; // rax
  unsigned int v12; // eax
  DWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v15[28]; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v17[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v14[0] = 0;
  memset_0(v15, 0, 0x68u);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( a2 )
  {
    v9 = 1;
    if ( a2 <= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0x90u);
  v8 = v7;
  if ( !v7 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"CoId=%hs:Insufficient memory for status indication", a1 + 552);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
    }
    LOWORD(a2) = 8;
    v9 = 0;
LABEL_13:
    a2 = (unsigned __int16)a2 | 0x80070000;
LABEL_14:
    v15[0] = *(_DWORD *)(a1 + 240);
    v15[6] = a2;
    v12 = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212440, (int)v15, 104, 0, 0, v14);
    if ( v12 )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v16) = 0;
        FormatRRASErrorString(&v16, L"CoId=%hs:Error completing MAKE_CALL_COMPLETE: %d", a1 + 552, v12);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
      }
    }
    DereferenceRefCount(a1 + 208);
    return v9;
  }
  *((_DWORD *)v7 + 8) = 17779;
  *((_DWORD *)v7 + 11) = *(_DWORD *)(a1 + 244);
  *((_DWORD *)v7 + 10) = *(_DWORD *)(a1 + 240);
  v9 = 1;
  *((_QWORD *)v7 + 6) = *(_QWORD *)(a1 + 472);
  *((_QWORD *)v7 + 7) = *(_QWORD *)(a1 + 480);
  v7[124] = *(_BYTE *)(a1 + 488);
  *((_DWORD *)v7 + 17) = *(_DWORD *)(a1 + 608);
  *(_OWORD *)(v7 + 72) = *(_OWORD *)(a1 + 489);
  *((_DWORD *)v7 + 22) = *(_DWORD *)(a1 + 505);
  *(_OWORD *)(v7 + 92) = *(_OWORD *)(a1 + 509);
  *(_OWORD *)(v7 + 108) = *(_OWORD *)(a1 + 525);
  *((_OWORD *)v7 + 8) = *a3;
  v10 = AsyncSstpDeviceControl(0x128018u, v7 + 40, 0x68u, v7 + 40, 0x68u, (LPOVERLAPPED)v7);
  if ( v10 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"CoId=%hs:AsyncMakeCallcomplete fails with %d", a1 + 552, v10);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v8);
    DereferenceRefCount(a1 + 208);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000da7c  mov     [rsp-8+arg_10], rbx
0x18000da81  mov     [rsp-8+arg_18], rsi
0x18000da86  push    rbp
0x18000da87  push    rdi
0x18000da88  push    r14
0x18000da8a  lea     rbp, [rsp-7D0h]
0x18000da92  sub     rsp, 8D0h
0x18000da99  mov     rax, cs:__security_cookie
0x18000daa0  xor     rax, rsp
0x18000daa3  mov     [rbp+7E0h+var_20], rax
0x18000daaa  mov     edi, edx
0x18000daac  mov     [rsp+8E0h+var_8A0], 0
0x18000dab4  xor     edx, edx; Val
0x18000dab6  mov     r14, r8
0x18000dab9  mov     rsi, rcx
0x18000dabc  lea     rcx, [rsp+8E0h+var_890]; void *
0x18000dac1  lea     r8d, [rdx+68h]; Size
0x18000dac5  call    memset_0
0x18000daca  xor     eax, eax
0x18000dacc  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18000dad0  xor     edx, edx; Val
0x18000dad2  mov     [rbp+7E0h+var_820], eax
0x18000dad5  mov     r8d, 7FCh; Size
0x18000dadb  call    memset_0
0x18000dae0  test    edi, edi
0x18000dae2  jnz     loc_18000DC86
0x18000dae8  call    cs:__imp_GetProcessHeap
0x18000daef  nop     dword ptr [rax+rax+00h]
0x18000daf4  lea     edx, [rdi+8]; dwFlags
0x18000daf7  mov     r8d, 90h; dwBytes
0x18000dafd  mov     rcx, rax; hHeap
0x18000db00  call    cs:__imp_HeapAlloc
0x18000db07  nop     dword ptr [rax+rax+00h]
0x18000db0c  mov     rdi, rax
0x18000db0f  test    rax, rax
0x18000db12  jnz     short loc_18000DB64
0x18000db14  test    cs:byte_18002E903, 8
0x18000db1b  jz      short loc_18000DB58
0x18000db1d  lea     r8, [rsi+228h]
0x18000db24  mov     word ptr [rbp+7E0h+var_820], ax
0x18000db28  lea     rdx, aCoidHsInsuffic; "CoId=%hs:Insufficient memory for status"...
0x18000db2f  lea     rcx, [rbp+7E0h+var_820]
0x18000db33  call    FormatRRASErrorString
0x18000db38  test    cs:byte_18002E903, 8
0x18000db3f  jz      short loc_18000DB58
0x18000db41  lea     r8, [rbp+7E0h+var_820]
0x18000db45  lea     rdx, RasSSTPSvcTraceError
0x18000db4c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000db53  call    McTemplateU0z_EventWriteTransfer
0x18000db58  mov     edi, 8
0x18000db5d  xor     bl, bl
0x18000db5f  jmp     loc_18000DC8A
0x18000db64  mov     dword ptr [rax+20h], 4573h
0x18000db6b  lea     rdx, [rdi+28h]; lpInBuffer
0x18000db6f  mov     eax, [rsi+0F4h]
0x18000db75  mov     r9, rdx; lpOutBuffer
0x18000db78  mov     [rdi+2Ch], eax
0x18000db7b  mov     ecx, 128018h; dwIoControlCode
0x18000db80  mov     eax, [rsi+0F0h]
0x18000db86  mov     r8d, 68h ; 'h'; nInBufferSize
0x18000db8c  mov     [rdx], eax
0x18000db8e  mov     bl, 1
0x18000db90  mov     rax, [rsi+1D8h]
0x18000db97  mov     [rdi+30h], rax
0x18000db9b  mov     rax, [rsi+1E0h]
0x18000dba2  mov     [rdi+38h], rax
0x18000dba6  mov     al, [rsi+1E8h]
0x18000dbac  mov     [rdi+7Ch], al
0x18000dbaf  mov     eax, [rsi+260h]
0x18000dbb5  mov     [rdi+44h], eax
0x18000dbb8  movups  xmm0, xmmword ptr [rsi+1E9h]
0x18000dbbf  mov     qword ptr [rsp+8E0h+var_8B8], rdi; LPOVERLAPPED
0x18000dbc4  mov     [rsp+8E0h+var_8C0], 68h ; 'h'; DWORD
0x18000dbcc  movups  xmmword ptr [rdi+48h], xmm0
0x18000dbd0  mov     eax, [rsi+1F9h]
0x18000dbd6  mov     [rdi+58h], eax
0x18000dbd9  movups  xmm0, xmmword ptr [rsi+1FDh]
0x18000dbe0  movups  xmmword ptr [rdi+5Ch], xmm0
0x18000dbe4  movups  xmm1, xmmword ptr [rsi+20Dh]
0x18000dbeb  movups  xmmword ptr [rdi+6Ch], xmm1
0x18000dbef  movups  xmm0, xmmword ptr [r14]
0x18000dbf3  movdqu  xmmword ptr [rdi+80h], xmm0
0x18000dbfb  call    AsyncSstpDeviceControl
0x18000dc00  test    eax, eax
0x18000dc02  jz      loc_18000DD38
0x18000dc08  test    cs:byte_18002E903, 8
0x18000dc0f  jz      short loc_18000DC53
0x18000dc11  xor     r8d, r8d
0x18000dc14  lea     rdx, aCoidHsAsyncmak; "CoId=%hs:AsyncMakeCallcomplete fails wi"...
0x18000dc1b  mov     word ptr [rbp+7E0h+var_820], r8w
0x18000dc20  lea     rcx, [rbp+7E0h+var_820]
0x18000dc24  lea     r8, [rsi+228h]
0x18000dc2b  mov     r9d, eax
0x18000dc2e  call    FormatRRASErrorString
0x18000dc33  test    cs:byte_18002E903, 8
0x18000dc3a  jz      short loc_18000DC53
0x18000dc3c  lea     r8, [rbp+7E0h+var_820]
0x18000dc40  lea     rdx, RasSSTPSvcTraceError
0x18000dc47  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dc4e  call    McTemplateU0z_EventWriteTransfer
0x18000dc53  call    cs:__imp_GetProcessHeap
0x18000dc5a  nop     dword ptr [rax+rax+00h]
0x18000dc5f  mov     r8, rdi; lpMem
0x18000dc62  xor     edx, edx; dwFlags
0x18000dc64  mov     rcx, rax; hHeap
0x18000dc67  call    cs:__imp_HeapFree
0x18000dc6e  nop     dword ptr [rax+rax+00h]
0x18000dc73  lea     rcx, [rsi+0D0h]
0x18000dc7a  call    DereferenceRefCount
0x18000dc7f  xor     bl, bl
0x18000dc81  jmp     loc_18000DD38
0x18000dc86  mov     bl, 1
0x18000dc88  jle     short loc_18000DC93
0x18000dc8a  movzx   edi, di
0x18000dc8d  or      edi, 80070000h
0x18000dc93  mov     eax, [rsi+0F0h]
0x18000dc99  lea     r8, [rsp+8E0h+var_890]; int
0x18000dc9e  mov     rcx, cs:SstpSvcGlobals
0x18000dca5  mov     r9d, 68h ; 'h'; int
0x18000dcab  mov     [rsp+8E0h+var_890], eax
0x18000dcaf  mov     edx, 128018h; int
0x18000dcb4  lea     rax, [rsp+8E0h+var_8A0]
0x18000dcb9  mov     [rsp+8E0h+var_878], edi
0x18000dcbd  mov     [rsp+8E0h+var_8B0], rax; LPDWORD
0x18000dcc2  mov     rcx, [rcx+118h]; int
0x18000dcc9  mov     [rsp+8E0h+var_8B8], 0; DWORD
0x18000dcd1  mov     qword ptr [rsp+8E0h+var_8C0], 0; LPVOID
0x18000dcda  call    SyncDeviceControl
0x18000dcdf  test    eax, eax
0x18000dce1  jz      short loc_18000DD2C
0x18000dce3  test    cs:byte_18002E903, 8
0x18000dcea  jz      short loc_18000DD2C
0x18000dcec  xor     ecx, ecx
0x18000dcee  lea     r8, [rsi+228h]
0x18000dcf5  mov     word ptr [rbp+7E0h+var_820], cx
0x18000dcf9  lea     rdx, aCoidHsErrorCom; "CoId=%hs:Error completing MAKE_CALL_COM"...
0x18000dd00  lea     rcx, [rbp+7E0h+var_820]
0x18000dd04  mov     r9d, eax
0x18000dd07  call    FormatRRASErrorString
0x18000dd0c  test    cs:byte_18002E903, 8
0x18000dd13  jz      short loc_18000DD2C
0x18000dd15  lea     r8, [rbp+7E0h+var_820]
0x18000dd19  lea     rdx, RasSSTPSvcTraceError
0x18000dd20  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dd27  call    McTemplateU0z_EventWriteTransfer
0x18000dd2c  lea     rcx, [rsi+0D0h]
0x18000dd33  call    DereferenceRefCount
0x18000dd38  mov     al, bl
0x18000dd3a  mov     rcx, [rbp+7E0h+var_20]
0x18000dd41  xor     rcx, rsp; StackCookie
0x18000dd44  call    __security_check_cookie
0x18000dd49  lea     r11, [rsp+8E0h+var_10]
0x18000dd51  mov     rbx, [r11+30h]
0x18000dd55  mov     rsi, [r11+38h]
0x18000dd59  mov     rsp, r11
0x18000dd5c  pop     r14
0x18000dd5e  pop     rdi
0x18000dd5f  pop     rbp
0x18000dd60  retn
```
