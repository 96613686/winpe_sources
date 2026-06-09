# SsAnnounce

- ea: `0x180006fb0`
- end: `0x180007474`
- name: `SsAnnounce`
- size: `1220`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006e04`

## callees

- `0x180006f00`
- `0x180006fb0`
- `0x180007480`
- `0x18001deb0`
- `0x1800215e8`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800071eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800071eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007088`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000722e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007088`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000722e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ae`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007290`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007290`
- `ntdll!RtlCopyUnicodeString` at `0x180007305`
- `ntdll!RtlCopyUnicodeString` at `0x18000732b`
- `ntdll!RtlCopyUnicodeString` at `0x180007305`
- `ntdll!RtlCopyUnicodeString` at `0x18000732b`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18000739b`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18000739b`
- `ntdll!RtlUnicodeStringToOemString` at `0x180007421`
- `ntdll!RtlUnicodeStringToOemString` at `0x180007469`
- `ntdll!RtlUnicodeStringToOemString` at `0x180007421`
- `ntdll!RtlUnicodeStringToOemString` at `0x180007469`
- `ntdll!RtlNtStatusToDosError` at `0x1800072e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800072e9`
- `ntdll!RtlInitUnicodeString` at `0x180007175`
- `ntdll!RtlInitUnicodeString` at `0x1800071ad`
- `ntdll!RtlInitUnicodeString` at `0x180007175`
- `ntdll!RtlInitUnicodeString` at `0x1800071ad`

## pseudocode

```c
char *__fastcall SsAnnounce(
        const void **a1,
        const WCHAR *a2,
        int a3,
        DWORD a4,
        int a5,
        int a6,
        __int64 a7,
        const WCHAR *a8,
        unsigned int a9)
{
  unsigned int v11; // r12d
  __int64 v12; // rbx
  __int64 v13; // rdi
  ULONG v14; // r15d
  SIZE_T v15; // rdx
  unsigned __int64 v16; // r8
  char *result; // rax
  char *lpOutBuffer; // r14
  char v19; // al
  int v20; // edi
  DWORD nOutBufferSize; // r12d
  const WCHAR *v22; // r15
  __int64 v23; // rbx
  NTSTATUS v24; // eax
  unsigned int v25; // edx
  DWORD v26; // esi
  char *v27; // rax
  char *v28; // rdi
  char *v29; // rbx
  char *v30; // rax
  __int64 v31; // rax
  char *v32; // rdi
  CHAR *v33; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-88h]
  _STRING v40; // [rsp+80h] [rbp-80h] BYREF
  _DWORD Src[6]; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING v42; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v43; // [rsp+B8h] [rbp-48h] BYREF
  int v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+CCh] [rbp-34h]
  int v46; // [rsp+D0h] [rbp-30h]
  char v47[556]; // [rsp+D4h] [rbp-2Ch] BYREF

  BytesReturned = a4;
  SourceString = a8;
  LODWORD(hDevice) = a3;
  v40 = 0;
  UnicodeString = 0;
  v11 = a9 & 0xFFFFFFFD;
  if ( !a6 )
    v11 = a9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_d164a289bda731438019be6a9e4466b0_Traceguids,
      (_DWORD)a8,
      v11);
  }
  v12 = -1;
  v13 = (unsigned int)*(unsigned __int16 *)a1 + 1;
  v36 = *(unsigned __int16 *)a1 + 1;
  if ( word_18005D560[0] )
  {
    v31 = -1;
    do
      ++v31;
    while ( word_18005D560[v31] );
    UnicodeString.Buffer = (PWSTR)word_18005D560;
    UnicodeString.Length = 2 * v31;
    UnicodeString.MaximumLength = 2 * v31 + 2;
    v14 = RtlxUnicodeStringToOemSize(&UnicodeString);
  }
  else
  {
    v14 = 1;
  }
  v15 = v14 + v13 + 75;
  v40.MaximumLength = v14;
  *(_QWORD *)&DestinationString.Length = (unsigned int)v13;
  v16 = v14 + 81LL;
  if ( v15 <= v16 )
    v15 = (unsigned int)v16;
  result = (char *)LocalAlloc(0x40u, v15);
  lpOutBuffer = result;
  if ( result )
  {
    if ( DWORD1(xmmword_18005CC48) && a5 )
    {
      *(_WORD *)result = 1;
      v32 = result + 10;
      *(_DWORD *)(result + 2) = v11;
      result[6] = xmmword_18005CBD0;
      result[7] = BYTE4(xmmword_18005CBD0);
      *((_WORD *)result + 4) = WORD2(xmmword_18005CBF0);
      memcpy_0(result + 10, a1[1], *(unsigned __int16 *)a1);
      v33 = &v32[*(_QWORD *)&DestinationString.Length];
      v32[*(unsigned __int16 *)a1] = 0;
      if ( v14 == 1 )
      {
        *v33 = 0;
      }
      else
      {
        v40.Buffer = v33;
        RtlUnicodeStringToOemString(&v40, &UnicodeString, 0);
      }
      SendSecondClassMailslot(SourceString, "\\MAILSLOT\\LANMAN", 0);
    }
    if ( (_DWORD)hDevice )
    {
      lpOutBuffer[1] = 0;
      v19 = 15;
      *((_DWORD *)lpOutBuffer + 7) = -1437269745;
      *((_DWORD *)lpOutBuffer + 6) = v11;
      v20 = v11 & 0x40000;
      if ( (v11 & 0x40000) == 0 )
        v19 = 1;
      *lpOutBuffer = v19;
      *(_DWORD *)(lpOutBuffer + 2) = 1000 * BytesReturned;
      lpOutBuffer[22] = xmmword_18005CBD0;
      lpOutBuffer[23] = BYTE4(xmmword_18005CBD0);
      memcpy_0(lpOutBuffer + 6, a1[1], *(unsigned __int16 *)a1);
      lpOutBuffer[*(unsigned __int16 *)a1 + 6] = 0;
      if ( v14 == 1 )
      {
        lpOutBuffer[32] = 0;
      }
      else
      {
        v40.Buffer = lpOutBuffer + 32;
        RtlUnicodeStringToOemString(&v40, &UnicodeString, 0);
      }
      nOutBufferSize = v14 + 32;
      v22 = SourceString;
      if ( (unsigned int)SendSecondClassMailslot(SourceString, "\\MAILSLOT\\BROWSE", (v20 != 0) + 29) )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v22);
        v42 = DestinationString;
        Src[1] = 6;
        RtlInitUnicodeString(&v43, a2);
        Src[0] = 3;
        v45 = 0;
        v44 = (v20 != 0) + 6;
        do
          ++v12;
        while ( a2[v12] );
        v46 = 2 * v12;
        _o_wcscpy_s(v47, 260);
        v23 = (unsigned int)(v46 + 68);
        hDevice = 0;
        BytesReturned = 0;
        v24 = OpenBrowser(&hDevice);
        if ( v24 < 0 )
        {
          RtlNtStatusToDosError(v24);
        }
        else
        {
          v25 = v23 + v42.MaximumLength;
          if ( v25 >= (unsigned int)v23 )
          {
            v26 = v25 + v43.MaximumLength;
            v27 = (char *)LocalAlloc(0x40u, v26);
            v28 = v27;
            if ( v27 )
            {
              memcpy_0(v27, Src, (unsigned int)v23);
              v29 = &v28[v23];
              if ( v42.Length )
              {
                *((_QWORD *)v28 + 4) = v29;
                *((_WORD *)v28 + 13) = v42.MaximumLength;
                RtlCopyUnicodeString((PUNICODE_STRING)(v28 + 24), &v42);
                v30 = &v29[v42.MaximumLength];
              }
              else
              {
                v30 = v29;
              }
              if ( v43.Length )
              {
                *((_QWORD *)v28 + 6) = v30;
                *((_WORD *)v28 + 21) = v43.MaximumLength;
                RtlCopyUnicodeString((PUNICODE_STRING)(v28 + 40), &v43);
              }
              if ( !DeviceIoControl(hDevice, 0x13004Bu, v28, v26, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
                GetLastError();
              LocalFree(v28);
              CloseHandle(hDevice);
            }
          }
        }
      }
    }
    return (char *)LocalFree(lpOutBuffer);
  }
  return result;
}

```

## disassembly

```asm
0x180006fb0  mov     [rsp-8+arg_10], rbx
0x180006fb5  push    rbp
0x180006fb6  push    rsi
0x180006fb7  push    rdi
0x180006fb8  push    r12
0x180006fba  push    r13
0x180006fbc  push    r14
0x180006fbe  push    r15
0x180006fc0  lea     rbp, [rsp-210h]
0x180006fc8  sub     rsp, 310h
0x180006fcf  mov     rax, cs:__security_cookie
0x180006fd6  xor     rax, rsp
0x180006fd9  mov     [rbp+240h+var_40], rax
0x180006fe0  mov     r13, rcx
0x180006fe3  mov     [rsp+340h+BytesReturned], r9d
0x180006fe8  mov     rcx, [rbp+240h+arg_38]
0x180006fef  xorps   xmm0, xmm0
0x180006ff2  xorps   xmm1, xmm1
0x180006ff5  mov     [rsp+340h+SourceString], rcx
0x180006ffa  mov     dword ptr [rsp+340h+hDevice], r8d
0x180006fff  mov     rsi, rdx
0x180007002  movups  xmmword ptr [rbp+240h+var_2C0.Length], xmm0
0x180007006  movups  xmmword ptr [rsp+340h+UnicodeString.Length], xmm1
0x18000700b  mov     r12d, [rbp+240h+arg_40]
0x180007012  lea     rdx, WPP_GLOBAL_Control
0x180007019  mov     rax, cs:WPP_GLOBAL_Control
0x180007020  and     r12d, 0FFFFFFFDh
0x180007024  cmp     [rbp+240h+arg_28], 0
0x18000702b  cmovz   r12d, [rbp+240h+arg_40]
0x180007033  cmp     rax, rdx
0x180007036  jnz     loc_180007336
0x18000703c  movzx   edi, word ptr [r13+0]
0x180007041  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007048  inc     edi
0x18000704a  cmp     cs:word_18005D560, 0
0x180007052  mov     [rsp+340h+var_2F0], edi
0x180007056  jnz     loc_18000736C
0x18000705c  mov     r15d, 1
0x180007062  mov     ecx, r15d
0x180007065  lea     rdx, [rdi+4Bh]
0x180007069  add     rdx, rcx
0x18000706c  mov     eax, edi
0x18000706e  mov     [rbp+240h+var_2C0.MaximumLength], r15w
0x180007073  mov     qword ptr [rsp+340h+DestinationString.Length], rax
0x180007078  lea     r8, [rcx+51h]
0x18000707c  mov     ecx, 40h ; '@'; uFlags
0x180007081  cmp     rdx, r8
0x180007084  cmovbe  edx, r8d; uBytes
0x180007088  call    cs:__imp_LocalAlloc
0x18000708e  mov     r14, rax
0x180007091  test    rax, rax
0x180007094  jz      loc_1800072BD
0x18000709a  cmp     dword ptr cs:xmmword_18005CC48+4, 0
0x1800070a1  jnz     loc_1800073A9
0x1800070a7  cmp     dword ptr [rsp+340h+hDevice], 0
0x1800070ac  jz      loc_1800072B4
0x1800070b2  mov     byte ptr [r14+1], 0
0x1800070b7  mov     eax, 0Fh
0x1800070bc  mov     dword ptr [r14+1Ch], 0AA55010Fh
0x1800070c4  mov     ecx, 1
0x1800070c9  mov     [r14+18h], r12d
0x1800070cd  mov     edi, r12d
0x1800070d0  and     edi, 40000h
0x1800070d6  cmovz   eax, ecx
0x1800070d9  lea     rcx, [r14+6]; void *
0x1800070dd  mov     [r14], al
0x1800070e0  imul    eax, [rsp+340h+BytesReturned], 3E8h
0x1800070e8  mov     [r14+2], eax
0x1800070ec  movzx   eax, byte ptr cs:xmmword_18005CBD0
0x1800070f3  mov     [r14+16h], al
0x1800070f7  movzx   eax, byte ptr cs:xmmword_18005CBD0+4
0x1800070fe  mov     [r14+17h], al
0x180007102  movzx   r8d, word ptr [r13+0]; Size
0x180007107  mov     rdx, [r13+8]; Src
0x18000710b  call    memcpy_0
0x180007110  movzx   eax, word ptr [r13+0]
0x180007115  mov     byte ptr [rax+r14+6], 0
0x18000711b  lea     rax, [r14+20h]
0x18000711f  cmp     r15d, 1
0x180007123  jnz     loc_180007459
0x180007129  mov     byte ptr [rax], 0
0x18000712c  lea     r12d, [r15+20h]
0x180007130  test    edi, edi
0x180007132  mov     r15, [rsp+340h+SourceString]
0x180007137  mov     r9, rsi
0x18000713a  setnz   al
0x18000713d  mov     r8d, r12d
0x180007140  add     al, 1Dh
0x180007142  mov     rdx, r14
0x180007145  mov     byte ptr [rsp+340h+nOutBufferSize], al; char
0x180007149  mov     rcx, r15; SourceString
0x18000714c  lea     rax, aMailslotBrowse; "\\MAILSLOT\\BROWSE"
0x180007153  mov     [rsp+340h+lpOutBuffer], rax; Src
0x180007158  call    SendSecondClassMailslot
0x18000715d  test    eax, eax
0x18000715f  jz      loc_1800072B4
0x180007165  xorps   xmm0, xmm0
0x180007168  lea     rcx, [rsp+340h+DestinationString]; DestinationString
0x18000716d  mov     rdx, r15; SourceString
0x180007170  movups  xmmword ptr [rsp+340h+DestinationString.Length], xmm0
0x180007175  call    cs:__imp_RtlInitUnicodeString
0x18000717b  movzx   eax, [rsp+340h+DestinationString.Length]
0x180007180  lea     rcx, [rbp+240h+var_288]; DestinationString
0x180007184  movsd   xmm0, qword ptr [rsp+340h+DestinationString+4]
0x18000718a  mov     rdx, rsi; SourceString
0x18000718d  mov     [rbp+240h+var_298.Length], ax
0x180007191  movzx   eax, [rsp+340h+DestinationString.MaximumLength]
0x180007196  mov     [rbp+240h+var_298.MaximumLength], ax
0x18000719a  mov     eax, dword ptr [rsp+340h+DestinationString.Buffer+4]
0x18000719e  mov     dword ptr [rbp+240h+var_298.Buffer+4], eax
0x1800071a1  mov     [rbp+240h+var_2AC], 6
0x1800071a8  movsd   qword ptr [rbp+240h+var_298+4], xmm0
0x1800071ad  call    cs:__imp_RtlInitUnicodeString
0x1800071b3  xor     r15d, r15d
0x1800071b6  mov     [rbp+240h+Src], 3
0x1800071bd  test    edi, edi
0x1800071bf  mov     [rbp+240h+var_274], r15d
0x1800071c3  mov     eax, r15d
0x1800071c6  setnz   al
0x1800071c9  add     eax, 6
0x1800071cc  mov     [rbp+240h+var_278], eax
0x1800071cf  nop
0x1800071d0  inc     rbx
0x1800071d3  cmp     [rsi+rbx*2], r15w
0x1800071d8  jnz     short loc_1800071D0
0x1800071da  add     ebx, ebx
0x1800071dc  lea     rcx, [rbp+240h+var_26C]
0x1800071e0  mov     r8, rsi
0x1800071e3  mov     [rbp+240h+var_270], ebx
0x1800071e6  mov     edx, 104h
0x1800071eb  call    cs:__imp__o_wcscpy_s
0x1800071f1  mov     ebx, [rbp+240h+var_270]
0x1800071f4  lea     rcx, [rsp+340h+hDevice]; FileHandle
0x1800071f9  add     ebx, 44h ; 'D'
0x1800071fc  mov     [rsp+340h+hDevice], r15
0x180007201  mov     [rsp+340h+BytesReturned], r15d
0x180007206  call    OpenBrowser
0x18000720b  test    eax, eax
0x18000720d  js      loc_1800072E7
0x180007213  movzx   edx, [rbp+240h+var_298.MaximumLength]
0x180007217  add     edx, ebx
0x180007219  cmp     edx, ebx
0x18000721b  jb      loc_1800072B4
0x180007221  movzx   esi, [rbp+240h+var_288.MaximumLength]
0x180007225  mov     ecx, 40h ; '@'; uFlags
0x18000722a  add     esi, edx
0x18000722c  mov     edx, esi; uBytes
0x18000722e  call    cs:__imp_LocalAlloc
0x180007234  mov     rdi, rax
0x180007237  test    rax, rax
0x18000723a  jz      short loc_1800072B4
0x18000723c  mov     r8d, ebx; Size
0x18000723f  lea     rdx, [rbp+240h+Src]; Src
0x180007243  mov     rcx, rax; void *
0x180007246  call    memcpy_0
0x18000724b  add     rbx, rdi
0x18000724e  cmp     [rbp+240h+var_298.Length], r15w
0x180007253  jnz     loc_1800072F1
0x180007259  mov     rax, rbx
0x18000725c  cmp     [rbp+240h+var_288.Length], r15w
0x180007261  jnz     loc_180007317
0x180007267  mov     rcx, [rsp+340h+hDevice]; hDevice
0x18000726c  lea     rax, [rsp+340h+BytesReturned]
0x180007271  mov     [rsp+340h+lpOverlapped], r15; lpOverlapped
0x180007276  mov     r9d, esi; nInBufferSize
0x180007279  mov     [rsp+340h+lpBytesReturned], rax; lpBytesReturned
0x18000727e  mov     r8, rdi; lpInBuffer
0x180007281  mov     [rsp+340h+nOutBufferSize], r12d; nOutBufferSize
0x180007286  mov     edx, 13004Bh; dwIoControlCode
0x18000728b  mov     [rsp+340h+lpOutBuffer], r14; lpOutBuffer
0x180007290  call    cs:__imp_DeviceIoControl
0x180007296  test    eax, eax
0x180007298  jnz     short loc_1800072A0
0x18000729a  call    cs:__imp_GetLastError
0x1800072a0  mov     rcx, rdi; hMem
0x1800072a3  call    cs:__imp_LocalFree
0x1800072a9  mov     rcx, [rsp+340h+hDevice]; hObject
0x1800072ae  call    cs:__imp_CloseHandle
0x1800072b4  mov     rcx, r14; hMem
0x1800072b7  call    cs:__imp_LocalFree
0x1800072bd  mov     rcx, [rbp+240h+var_40]
0x1800072c4  xor     rcx, rsp; StackCookie
0x1800072c7  call    __security_check_cookie
0x1800072cc  mov     rbx, [rsp+340h+arg_10]
0x1800072d4  add     rsp, 310h
0x1800072db  pop     r15
0x1800072dd  pop     r14
0x1800072df  pop     r13
0x1800072e1  pop     r12
0x1800072e3  pop     rdi
0x1800072e4  pop     rsi
0x1800072e5  pop     rbp
0x1800072e6  retn
0x1800072e7  mov     ecx, eax; Status
0x1800072e9  call    cs:__imp_RtlNtStatusToDosError
0x1800072ef  jmp     short loc_1800072B4
0x1800072f1  mov     [rdi+20h], rbx
0x1800072f5  lea     rdx, [rbp+240h+var_298]; SourceString
0x1800072f9  movzx   ecx, [rbp+240h+var_298.MaximumLength]
0x1800072fd  mov     [rdi+1Ah], cx
0x180007301  lea     rcx, [rdi+18h]; DestinationString
0x180007305  call    cs:__imp_RtlCopyUnicodeString
0x18000730b  movzx   eax, [rbp+240h+var_298.MaximumLength]
0x18000730f  add     rax, rbx
0x180007312  jmp     loc_18000725C
0x180007317  mov     [rdi+30h], rax
0x18000731b  lea     rcx, [rdi+28h]; DestinationString
0x18000731f  movzx   eax, [rbp+240h+var_288.MaximumLength]
0x180007323  lea     rdx, [rbp+240h+var_288]; SourceString
0x180007327  mov     [rdi+2Ah], ax
0x18000732b  call    cs:__imp_RtlCopyUnicodeString
0x180007331  jmp     loc_180007267
0x180007336  test    byte ptr [rax+1Ch], 1
0x18000733a  jz      loc_18000703C
0x180007340  cmp     byte ptr [rax+19h], 2
0x180007344  jb      loc_18000703C
0x18000734a  mov     r9, rcx
0x18000734d  mov     dword ptr [rsp+340h+lpOutBuffer], r12d
0x180007352  mov     rcx, [rax+10h]
0x180007356  lea     r8, WPP_d164a289bda731438019be6a9e4466b0_Traceguids
0x18000735d  mov     edx, 15h
0x180007362  call    WPP_SF_Sd
0x180007367  jmp     loc_18000703C
0x18000736c  lea     rcx, word_18005D560
0x180007373  mov     rax, rbx
0x180007376  inc     rax
0x180007379  cmp     word ptr [rcx+rax*2], 0
0x18000737e  jnz     short loc_180007376
0x180007380  add     ax, ax
0x180007383  mov     [rsp+340h+UnicodeString.Buffer], rcx
0x180007388  mov     [rsp+340h+UnicodeString.Length], ax
0x18000738d  lea     rcx, [rsp+340h+UnicodeString]; UnicodeString
0x180007392  add     ax, 2
0x180007396  mov     [rsp+340h+UnicodeString.MaximumLength], ax
0x18000739b  call    cs:__imp_RtlxUnicodeStringToOemSize
0x1800073a1  mov     r15d, eax
0x1800073a4  jmp     loc_180007062
0x1800073a9  cmp     [rbp+240h+arg_20], 0
0x1800073b0  jz      loc_1800070A7
0x1800073b6  mov     word ptr [rax], 1
0x1800073bb  lea     rdi, [r14+0Ah]
0x1800073bf  mov     [rax+2], r12d
0x1800073c3  movzx   ecx, byte ptr cs:xmmword_18005CBD0
0x1800073ca  mov     [rax+6], cl
0x1800073cd  mov     rcx, rdi; void *
0x1800073d0  movzx   eax, byte ptr cs:xmmword_18005CBD0+4
0x1800073d7  mov     [r14+7], al
0x1800073db  movzx   eax, word ptr cs:xmmword_18005CBF0+4
0x1800073e2  mov     [r14+8], ax
0x1800073e7  movzx   r8d, word ptr [r13+0]; Size
0x1800073ec  mov     rdx, [r13+8]; Src
0x1800073f0  call    memcpy_0
0x1800073f5  movzx   eax, word ptr [r13+0]
0x1800073fa  mov     rcx, qword ptr [rsp+340h+DestinationString.Length]
0x1800073ff  add     rcx, rdi
0x180007402  mov     byte ptr [rax+rdi], 0
0x180007406  cmp     r15d, 1
0x18000740a  jnz     short loc_180007411
0x18000740c  mov     byte ptr [rcx], 0
0x18000740f  jmp     short loc_180007427
0x180007411  mov     [rbp+240h+var_2C0.Buffer], rcx
0x180007415  lea     rdx, [rsp+340h+UnicodeString]; SourceString
0x18000741a  lea     rcx, [rbp+240h+var_2C0]; DestinationString
0x18000741e  xor     r8d, r8d; AllocateDestinationString
0x180007421  call    cs:__imp_RtlUnicodeStringToOemString
0x180007427  mov     r8d, [rsp+340h+var_2F0]
0x18000742c  lea     rax, aMailslotLanman; "\\MAILSLOT\\LANMAN"
0x180007433  mov     rcx, [rsp+340h+SourceString]; SourceString
0x180007438  add     r8d, 0Ah
0x18000743c  add     r8d, r15d
0x18000743f  mov     byte ptr [rsp+340h+nOutBufferSize], 0; char
0x180007444  mov     r9, rsi
0x180007447  mov     [rsp+340h+lpOutBuffer], rax; Src
0x18000744c  mov     rdx, r14
0x18000744f  call    SendSecondClassMailslot
0x180007454  jmp     loc_1800070A7
0x180007459  xor     r8d, r8d; AllocateDestinationString
0x18000745c  mov     [rbp+240h+var_2C0.Buffer], rax
0x180007460  lea     rdx, [rsp+340h+UnicodeString]; SourceString
0x180007465  lea     rcx, [rbp+240h+var_2C0]; DestinationString
0x180007469  call    cs:__imp_RtlUnicodeStringToOemString
0x18000746f  jmp     loc_18000712C
```
