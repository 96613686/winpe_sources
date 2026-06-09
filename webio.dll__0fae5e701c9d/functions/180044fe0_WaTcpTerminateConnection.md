# WaTcpTerminateConnection

- ea: `0x180044fe0`
- end: `0x18004523d`
- name: `WaTcpTerminateConnection`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180006104`
- `0x180013820`
- `0x180014f04`
- `0x18002187c`
- `0x180021e84`
- `0x180044fe0`
- `0x1800452d4`
- `0x1800923bc`
- `0x180092564`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800450a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800450a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045183`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045183`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180045038`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180045038`
- `WS2_32!__imp_closesocket` at `0x1800450db`
- `WS2_32!__imp_closesocket` at `0x1800450db`

## pseudocode

```c
void __fastcall WaTcpTerminateConnection(__int64 a1, int a2)
{
  __int64 *v2; // rbx
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rcx
  __int64 v5; // r9
  struct _TP_IO *v6; // rcx
  __int64 v7; // r9
  volatile signed __int32 *v8; // rcx
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rcx
  volatile signed __int32 *v11; // rcx
  _QWORD v12[3]; // [rsp+40h] [rbp-18h] BYREF

  v2 = (__int64 *)(a1 + 48);
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qq(1027, 10, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1, *v2);
  v3 = *v2;
  v4 = *(volatile signed __int32 **)(v3 + 336);
  if ( v4 && _InterlockedExchangeAdd(v4 + 1, 0xFFFFFFFF) == 1 )
    WapFreeDnsQueryResult((LPVOID)v4);
  v5 = *(_QWORD *)(v3 + 704);
  if ( v5 != -1 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
      McTemplateU0pxqqxt_EventWriteTransfer((_DWORD)v4, a2, *(_QWORD *)(v3 + 8), v5, 8, 0, 0, 0);
    closesocket(*(_QWORD *)(v3 + 704));
  }
  v6 = *(struct _TP_IO **)(v3 + 712);
  if ( v6 )
    CloseThreadpoolIo(v6);
  v7 = *(_QWORD *)(v3 + 288);
  if ( v7 )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 11, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v7);
    CloseHandle(*(HANDLE *)(v3 + 288));
    *(_QWORD *)(v3 + 288) = 0;
  }
  v8 = *(volatile signed __int32 **)(v3 + 360);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
    {
      v12[0] = v8;
      WxFreeHeapEx(v12);
    }
    *(_QWORD *)(v3 + 360) = 0;
  }
  v9 = *(_QWORD *)(v3 + 472);
  if ( v9 )
  {
    WaDereferenceDnsCache(v9);
    *(_QWORD *)(v3 + 472) = 0;
  }
  v10 = *(volatile signed __int32 **)(v3 + 480);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 1, 0xFFFFFFFF) == 1 )
      WapUriFreeUriObject((LPVOID)v10);
    *(_QWORD *)(v3 + 480) = 0;
  }
  v11 = *(volatile signed __int32 **)(v3 + 488);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11, 0xFFFFFFFF) == 1 )
    {
      v12[0] = v11;
      WxFreeHeapEx(v12);
    }
    *(_QWORD *)(v3 + 488) = 0;
  }
  if ( *(_BYTE *)(v3 + 371) )
  {
    WaTpTerminateWorkItem(v3 + 408);
    *(_BYTE *)(v3 + 371) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  *(_DWORD *)v3 = 1668309876;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_(1027, 12, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
}

```

## disassembly

```asm
0x180044fe0  push    rbx
0x180044fe2  sub     rsp, 50h
0x180044fe6  mov     r9, rcx
0x180044fe9  test    byte ptr cs:xmmword_1800AD720, 8
0x180044ff0  lea     rbx, [rcx+30h]
0x180044ff4  jnz     loc_18004513A
0x180044ffa  mov     rbx, [rbx]
0x180044ffd  mov     rcx, [rbx+150h]; lpMem
0x180045004  test    rcx, rcx
0x180045007  jz      short loc_18004501B
0x180045009  or      eax, 0FFFFFFFFh
0x18004500c  lock xadd [rcx+4], eax
0x180045011  cmp     eax, 1
0x180045014  jnz     short loc_18004501B
0x180045016  call    WapFreeDnsQueryResult
0x18004501b  mov     r9, [rbx+2C0h]
0x180045022  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180045026  jnz     loc_1800450CB
0x18004502c  mov     rcx, [rbx+2C8h]; pio
0x180045033  test    rcx, rcx
0x180045036  jz      short loc_180045044
0x180045038  call    cs:__imp_CloseThreadpoolIo
0x18004503f  nop     dword ptr [rax+rax+00h]
0x180045044  mov     r9, [rbx+120h]
0x18004504b  test    r9, r9
0x18004504e  jnz     loc_18004515D
0x180045054  mov     rcx, [rbx+168h]
0x18004505b  test    rcx, rcx
0x18004505e  jnz     loc_18004519F
0x180045064  mov     rcx, [rbx+1D8h]
0x18004506b  test    rcx, rcx
0x18004506e  jnz     loc_1800451CA
0x180045074  mov     rcx, [rbx+1E0h]; lpMem
0x18004507b  test    rcx, rcx
0x18004507e  jnz     loc_180045118
0x180045084  mov     rcx, [rbx+1E8h]
0x18004508b  test    rcx, rcx
0x18004508e  jnz     loc_1800451DF
0x180045094  cmp     byte ptr [rbx+173h], 0
0x18004509b  jnz     loc_18004520A
0x1800450a1  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800450a5  call    cs:__imp_DeleteCriticalSection
0x1800450ac  nop     dword ptr [rax+rax+00h]
0x1800450b1  mov     dword ptr [rbx], 63706374h
0x1800450b7  test    byte ptr cs:xmmword_1800AD720, 8
0x1800450be  jnz     loc_180045222
0x1800450c4  add     rsp, 50h
0x1800450c8  pop     rbx
0x1800450c9  retn
0x1800450cb  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x1800450d2  jnz     short loc_1800450EC
0x1800450d4  mov     rcx, [rbx+2C0h]; s
0x1800450db  call    cs:__imp_closesocket
0x1800450e2  nop     dword ptr [rax+rax+00h]
0x1800450e7  jmp     loc_18004502C
0x1800450ec  mov     r8, [rbx+8]
0x1800450f0  mov     [rsp+58h+var_20], 0
0x1800450f8  mov     [rsp+58h+var_28], 0
0x180045101  mov     [rsp+58h+var_30], 0
0x180045109  mov     dword ptr [rsp+58h+var_38], 8
0x180045111  call    McTemplateU0pxqqxt_EventWriteTransfer
0x180045116  jmp     short loc_1800450D4
0x180045118  or      eax, 0FFFFFFFFh
0x18004511b  lock xadd [rcx+4], eax
0x180045120  cmp     eax, 1
0x180045123  jnz     short loc_18004512A
0x180045125  call    WapUriFreeUriObject
0x18004512a  mov     qword ptr [rbx+1E0h], 0
0x180045135  jmp     loc_180045084
0x18004513a  mov     rax, [rbx]
0x18004513d  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180045144  mov     edx, 0Ah
0x180045149  mov     [rsp+58h+var_38], rax
0x18004514e  mov     ecx, 403h
0x180045153  call    WPP_SF_qq
0x180045158  jmp     loc_180044FFA
0x18004515d  test    byte ptr cs:xmmword_1800AD720, 8
0x180045164  jz      short loc_18004517C
0x180045166  mov     edx, 0Bh
0x18004516b  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180045172  mov     ecx, 403h
0x180045177  call    WPP_SF_q
0x18004517c  mov     rcx, [rbx+120h]; hObject
0x180045183  call    cs:__imp_CloseHandle
0x18004518a  nop     dword ptr [rax+rax+00h]
0x18004518f  mov     qword ptr [rbx+120h], 0
0x18004519a  jmp     loc_180045054
0x18004519f  or      eax, 0FFFFFFFFh
0x1800451a2  lock xadd [rcx], eax
0x1800451a6  cmp     eax, 1
0x1800451a9  jnz     short loc_1800451BA
0x1800451ab  mov     [rsp+58h+var_18], rcx
0x1800451b0  lea     rcx, [rsp+58h+var_18]
0x1800451b5  call    WxFreeHeapEx
0x1800451ba  mov     qword ptr [rbx+168h], 0
0x1800451c5  jmp     loc_180045064
0x1800451ca  call    WaDereferenceDnsCache
0x1800451cf  mov     qword ptr [rbx+1D8h], 0
0x1800451da  jmp     loc_180045074
0x1800451df  or      eax, 0FFFFFFFFh
0x1800451e2  lock xadd [rcx], eax
0x1800451e6  cmp     eax, 1
0x1800451e9  jnz     short loc_1800451FA
0x1800451eb  mov     [rsp+58h+var_18], rcx
0x1800451f0  lea     rcx, [rsp+58h+var_18]
0x1800451f5  call    WxFreeHeapEx
0x1800451fa  mov     qword ptr [rbx+1E8h], 0
0x180045205  jmp     loc_180045094
0x18004520a  lea     rcx, [rbx+198h]
0x180045211  call    WaTpTerminateWorkItem
0x180045216  mov     byte ptr [rbx+173h], 0
0x18004521d  jmp     loc_1800450A1
0x180045222  mov     edx, 0Ch
0x180045227  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18004522e  mov     ecx, 403h
0x180045233  add     rsp, 50h
0x180045237  pop     rbx
0x180045238  jmp     WPP_SF_
```
