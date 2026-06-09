# CreateIconIndirect

- ea: `0x180005950`
- end: `0x180005d42`
- name: `CreateIconIndirect`
- size: `1010`
- prototype: `HICON __stdcall(PICONINFO piconinfo)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003be0`
- `0x18007ebb4`

## callees

- `0x180004cd0`
- `0x180005950`
- `0x180005d48`
- `0x180005d94`
- `0x180005f7c`
- `0x180008324`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserSetCursorIconDataEx` at `0x180005c3d`
- `win32u!NtUserSetCursorIconDataEx` at `0x180005c3d`
- `win32u!NtUserDestroyCursor` at `0x180005cb4`
- `win32u!NtUserDestroyCursor` at `0x180005cb4`
- `win32u!NtUserCreateEmptyCursorObject` at `0x180005a00`
- `win32u!NtUserCreateEmptyCursorObject` at `0x180005a00`
- `ntdll!RtlLeaveCriticalSection` at `0x180005abb`
- `ntdll!RtlLeaveCriticalSection` at `0x180005ba0`
- `ntdll!RtlLeaveCriticalSection` at `0x180005c8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180005abb`
- `ntdll!RtlLeaveCriticalSection` at `0x180005ba0`
- `ntdll!RtlLeaveCriticalSection` at `0x180005c8b`
- `ntdll!RtlInitUnicodeString` at `0x180005bfe`
- `ntdll!RtlInitUnicodeString` at `0x180005d1a`
- `ntdll!RtlInitUnicodeString` at `0x180005bfe`
- `ntdll!RtlInitUnicodeString` at `0x180005d1a`
- `ntdll!RtlFreeHeap` at `0x180005aae`
- `ntdll!RtlFreeHeap` at `0x180005aae`
- `GDI32!SelectObject` at `0x180005b1f`
- `GDI32!SelectObject` at `0x180005b33`
- `GDI32!SelectObject` at `0x180005b7a`
- `GDI32!SelectObject` at `0x180005b8a`
- `GDI32!SelectObject` at `0x180005b1f`
- `GDI32!SelectObject` at `0x180005b33`
- `GDI32!SelectObject` at `0x180005b7a`
- `GDI32!SelectObject` at `0x180005b8a`
- `GDI32!GetObjectW` at `0x1800059b5`
- `GDI32!GetObjectW` at `0x1800059dc`
- `GDI32!GetObjectW` at `0x1800059b5`
- `GDI32!GetObjectW` at `0x1800059dc`
- `GDI32!GdiTrackHDelete` at `0x180005c4b`
- `GDI32!GdiTrackHDelete` at `0x180005c55`
- `GDI32!GdiTrackHDelete` at `0x180005c4b`
- `GDI32!GdiTrackHDelete` at `0x180005c55`
- `GDI32!CreateBitmap` at `0x180005adf`
- `GDI32!CreateBitmap` at `0x180005adf`
- `GDI32!DeleteDC` at `0x180005b93`
- `GDI32!DeleteDC` at `0x180005b93`
- `GDI32!BitBlt` at `0x180005b6e`
- `GDI32!BitBlt` at `0x180005b6e`
- `GDI32!CreateCompatibleDC` at `0x180005b06`
- `GDI32!CreateCompatibleDC` at `0x180005b06`
- `GDI32!DeleteObject` at `0x180005c9a`
- `GDI32!DeleteObject` at `0x180005ca9`
- `GDI32!DeleteObject` at `0x180005c9a`
- `GDI32!DeleteObject` at `0x180005ca9`

## pseudocode

```c
HICON __stdcall CreateIconIndirect(PICONINFO piconinfo)
{
  HBITMAP hbmMask; // rcx
  HBITMAP hbmColor; // rcx
  unsigned int v4; // r14d
  HICON EmptyCursorObject; // rsi
  HBITMAP v6; // rdi
  int v7; // ecx
  HDC v8; // rdx
  HBITMAP v9; // rbx
  struct tagBITMAPINFOHEADER *v10; // rax
  struct tagBITMAPINFOHEADER *v11; // rdi
  int Buffer; // edx
  HDC CompatibleDC; // rax
  HDC v14; // r12
  HGDIOBJ v15; // rdi
  HGDIOBJ v16; // rbx
  unsigned int v17; // eax
  int ThreadDefCursorSize; // eax
  int v19; // ebx
  struct _UNICODE_STRING *v20; // r8
  unsigned int v22; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v23; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING pv[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-38h]
  PCWSTR v31[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v32; // [rsp+F0h] [rbp-10h]
  __int16 xHotspot; // [rsp+FCh] [rbp-4h]
  __int16 v34; // [rsp+FEh] [rbp-2h]
  HGDIOBJ h; // [rsp+100h] [rbp+0h]
  HGDIOBJ ho; // [rsp+108h] [rbp+8h]
  int v37; // [rsp+130h] [rbp+30h]
  int nWidth; // [rsp+134h] [rbp+34h]
  int nHeight; // [rsp+138h] [rbp+38h]

  memset_0(v31, 0, 0x88u);
  hbmMask = piconinfo->hbmMask;
  memset(pv, 0, sizeof(pv));
  v29 = 0;
  v30 = 0;
  if ( !GetObjectW(hbmMask, 32, pv) )
    return 0;
  hbmColor = piconinfo->hbmColor;
  v4 = 0;
  if ( hbmColor )
  {
    if ( !GetObjectW(hbmColor, 32, &v29) )
      return 0;
    if ( (_DWORD)v30 == 2097153 )
      v4 = 2048;
  }
  EmptyCursorObject = (HICON)NtUserCreateEmptyCursorObject(0);
  if ( !EmptyCursorObject )
    return 0;
  memset_0(v31, 0, 0x88u);
  v6 = piconinfo->hbmColor;
  v7 = *(_DWORD *)(&pv[0].MaximumLength + 1);
  nWidth = *(_DWORD *)(&pv[0].MaximumLength + 1);
  if ( v6 )
  {
    nHeight = 2 * LODWORD(pv[0].Buffer);
    v37 = (unsigned __int16)v30 * WORD1(v30);
    if ( !(unsigned int)AcquireGlobalGdiResources() )
    {
      ho = 0;
      goto LABEL_24;
    }
    v22 = 0;
    v9 = 0;
    v10 = (struct tagBITMAPINFOHEADER *)DIBFromBitmap(v6, v8, &v22);
    v11 = v10;
    if ( v10 )
    {
      v9 = ConvertDIBBitmap(v10, v22, 0, 0, v4, 0, 0, 0, 0);
      RtlFreeHeap(pUserHeap, 0, v11);
    }
    RtlLeaveCriticalSection(&gcsHdc);
    ho = v9;
    if ( !v9 )
      goto LABEL_24;
    Buffer = nHeight;
    v7 = nWidth;
  }
  else
  {
    Buffer = (int)pv[0].Buffer;
    nHeight = (int)pv[0].Buffer;
    v37 = 1;
  }
  h = CreateBitmap(v7, Buffer, 1u, 1u, 0);
  if ( !h || !(unsigned int)AcquireGlobalGdiResources() )
    goto LABEL_24;
  CompatibleDC = CreateCompatibleDC(ghdcBits2);
  v14 = CompatibleDC;
  if ( !CompatibleDC )
  {
    RtlLeaveCriticalSection(&gcsHdc);
LABEL_24:
    if ( h )
      DeleteObject(h);
    if ( ho )
      DeleteObject(ho);
    NtUserDestroyCursor(EmptyCursorObject, 0);
    return 0;
  }
  v15 = SelectObject(CompatibleDC, h);
  v16 = SelectObject(ghdcBits2, piconinfo->hbmMask);
  BitBlt(v14, 0, 0, *(int *)(&pv[0].MaximumLength + 1), (int)pv[0].Buffer, ghdcBits2, 0, 0, 0xCC0020u);
  SelectObject(v14, v15);
  SelectObject(ghdcBits2, v16);
  DeleteDC(v14);
  RtlLeaveCriticalSection(&gcsHdc);
  if ( piconinfo->fIcon )
  {
    v32 = 3;
    xHotspot = (unsigned int)nWidth >> 1;
    v17 = (unsigned int)nHeight >> 2;
  }
  else
  {
    xHotspot = piconinfo->xHotspot;
    LOWORD(v17) = piconinfo->yHotspot;
    v32 = 1;
  }
  v34 = v17;
  ThreadDefCursorSize = GetThreadDefCursorSize();
  *(_QWORD *)&DestinationString.Length = 0;
  v19 = ThreadDefCursorSize;
  DestinationString.Buffer = 0;
  v28 = 0;
  p_DestinationString = &DestinationString;
  v23 = 0;
  v24 = 0;
  RtlInitUnicodeString(&DestinationString, v31[1]);
  v20 = &v23;
  DWORD2(v24) = 0;
  *(_QWORD *)&v24 = &v23;
  if ( ((unsigned __int64)v31[0] & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    RtlInitUnicodeString(&v23, v31[0]);
    v20 = (struct _UNICODE_STRING *)v24;
  }
  else
  {
    *(_DWORD *)&v23.Length = 0;
    v23.Buffer = (PWSTR)v31[0];
  }
  if ( !(unsigned int)NtUserSetCursorIconDataEx(EmptyCursorObject, p_DestinationString, v20, v31, v19) )
    goto LABEL_24;
  GdiTrackHDelete(h);
  GdiTrackHDelete(ho);
  if ( v32 == 1 && (unsigned int)(LODWORD(NtCurrentTeb()->Win32ClientInfo[34]) - 1) > 1 )
    CreateDpiCursors(EmptyCursorObject, 0, 0, nWidth, (unsigned int)nHeight >> 1, v4);
  return EmptyCursorObject;
}

```

## disassembly

```asm
0x180005950  push    rbp
0x180005952  push    rbx
0x180005953  push    rsi
0x180005954  push    rdi
0x180005955  push    r12
0x180005957  push    r13
0x180005959  push    r14
0x18000595b  push    r15
0x18000595d  lea     rbp, [rsp-88h]
0x180005965  sub     rsp, 188h
0x18000596c  mov     rax, cs:__security_cookie
0x180005973  xor     rax, rsp
0x180005976  mov     [rbp+0C0h+var_50], rax
0x18000597a  mov     r15, rcx
0x18000597d  mov     edi, 88h
0x180005982  mov     r8d, edi; Size
0x180005985  lea     rcx, [rbp+0C0h+var_E0]; void *
0x180005989  xor     edx, edx; Val
0x18000598b  call    memset_0
0x180005990  mov     rcx, [r15+10h]; h
0x180005994  lea     ebx, [rdi-68h]
0x180005997  xorps   xmm0, xmm0
0x18000599a  lea     r8, [rsp+1C0h+pv]; pv
0x18000599f  xorps   xmm1, xmm1
0x1800059a2  mov     edx, ebx; c
0x1800059a4  movups  [rsp+1C0h+pv], xmm0
0x1800059a9  movups  [rbp+0C0h+var_138], xmm0
0x1800059ad  movups  [rbp+0C0h+var_108], xmm1
0x1800059b1  movups  [rbp+0C0h+var_F8], xmm1
0x1800059b5  call    cs:__imp_GetObjectW
0x1800059bb  xor     r13d, r13d
0x1800059be  test    eax, eax
0x1800059c0  jz      loc_180005CBA
0x1800059c6  mov     rcx, [r15+18h]; h
0x1800059ca  lea     r12d, [rbx-1Fh]
0x1800059ce  mov     r14d, r13d
0x1800059d1  test    rcx, rcx
0x1800059d4  jz      short loc_1800059FE
0x1800059d6  lea     r8, [rbp+0C0h+var_108]; pv
0x1800059da  mov     edx, ebx; c
0x1800059dc  call    cs:__imp_GetObjectW
0x1800059e2  test    eax, eax
0x1800059e4  jz      loc_180005CBA
0x1800059ea  cmp     word ptr [rbp+0C0h+var_F8], r12w
0x1800059ef  jnz     short loc_1800059FE
0x1800059f1  cmp     word ptr [rbp+0C0h+var_F8+2], bx
0x1800059f5  mov     eax, 800h
0x1800059fa  cmovz   r14d, eax
0x1800059fe  xor     ecx, ecx
0x180005a00  call    cs:__imp_NtUserCreateEmptyCursorObject
0x180005a06  mov     rsi, rax
0x180005a09  test    rax, rax
0x180005a0c  jz      loc_180005CBA
0x180005a12  mov     r8, rdi; Size
0x180005a15  lea     rcx, [rbp+0C0h+var_E0]; void *
0x180005a19  xor     edx, edx; Val
0x180005a1b  call    memset_0
0x180005a20  mov     rdi, [r15+18h]
0x180005a24  mov     ecx, dword ptr [rsp+1C0h+pv+4]
0x180005a28  mov     [rbp+0C0h+nWidth], ecx
0x180005a2b  test    rdi, rdi
0x180005a2e  jz      loc_180005D2A
0x180005a34  mov     eax, dword ptr [rbp+0C0h+pv+8]
0x180005a37  movzx   ecx, word ptr [rbp+0C0h+var_F8+2]
0x180005a3b  add     eax, eax
0x180005a3d  mov     [rbp+0C0h+nHeight], eax
0x180005a40  movzx   eax, word ptr [rbp+0C0h+var_F8]
0x180005a44  imul    ecx, eax
0x180005a47  mov     [rbp+0C0h+var_90], ecx
0x180005a4a  call    ?AcquireGlobalGdiResources@@YAHXZ; AcquireGlobalGdiResources(void)
0x180005a4f  test    eax, eax
0x180005a51  jz      loc_180005D39
0x180005a57  lea     r8, [rsp+1C0h+var_170]; unsigned int *
0x180005a5c  mov     [rsp+1C0h+var_170], r13d
0x180005a61  mov     rcx, rdi; hbm
0x180005a64  mov     rbx, r13
0x180005a67  call    ?DIBFromBitmap@@YAPEAXPEAUHBITMAP__@@PEAUHDC__@@PEAK@Z; DIBFromBitmap(HBITMAP__ *,HDC__ *,ulong *)
0x180005a6c  mov     rdi, rax
0x180005a6f  test    rax, rax
0x180005a72  jz      short loc_180005AB4
0x180005a74  mov     edx, [rsp+1C0h+var_170]; unsigned int
0x180005a78  xor     r9d, r9d; unsigned int
0x180005a7b  mov     qword ptr [rsp+1C0h+rop], r13; unsigned int *
0x180005a80  xor     r8d, r8d; unsigned int
0x180005a83  mov     qword ptr [rsp+1C0h+y1], r13; char **
0x180005a88  mov     rcx, rax; struct tagBITMAPINFOHEADER *
0x180005a8b  mov     qword ptr [rsp+1C0h+x1], r13; struct tagBITMAPINFOHEADER **
0x180005a90  mov     [rsp+1C0h+hdcSrc], r13; struct tagBITMAPINFOHEADER *
0x180005a95  mov     dword ptr [rsp+1C0h+lpBits], r14d; unsigned int
0x180005a9a  call    ?ConvertDIBBitmap@@YAPEAUHBITMAP__@@PEFAUtagBITMAPINFOHEADER@@KKKIPEAU2@PEAPEAU2@PEAPEADPEAK@Z; ConvertDIBBitmap(tagBITMAPINFOHEADER *,ulong,ulong,ulong,uint,tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER * *,char * *,ulong *)
0x180005a9f  mov     rcx, cs:pUserHeap; HeapHandle
0x180005aa6  mov     r8, rdi; P
0x180005aa9  xor     edx, edx; Flags
0x180005aab  mov     rbx, rax
0x180005aae  call    cs:__imp_RtlFreeHeap
0x180005ab4  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180005abb  call    cs:__imp_RtlLeaveCriticalSection
0x180005ac1  mov     [rbp+0C0h+ho], rbx
0x180005ac5  test    rbx, rbx
0x180005ac8  jz      loc_180005C91
0x180005ace  mov     edx, [rbp+0C0h+nHeight]; nHeight
0x180005ad1  mov     ecx, [rbp+0C0h+nWidth]; nWidth
0x180005ad4  mov     r9d, r12d; nBitCount
0x180005ad7  mov     [rsp+1C0h+lpBits], r13; lpBits
0x180005adc  mov     r8d, r12d; nPlanes
0x180005adf  call    cs:__imp_CreateBitmap
0x180005ae5  mov     [rbp+0C0h+h], rax
0x180005ae9  test    rax, rax
0x180005aec  jz      loc_180005C91
0x180005af2  call    ?AcquireGlobalGdiResources@@YAHXZ; AcquireGlobalGdiResources(void)
0x180005af7  test    eax, eax
0x180005af9  jz      loc_180005C91
0x180005aff  mov     rcx, cs:ghdcBits2; hdc
0x180005b06  call    cs:__imp_CreateCompatibleDC
0x180005b0c  mov     r12, rax
0x180005b0f  test    rax, rax
0x180005b12  jz      loc_180005C84
0x180005b18  mov     rdx, [rbp+0C0h+h]; h
0x180005b1c  mov     rcx, rax; hdc
0x180005b1f  call    cs:__imp_SelectObject
0x180005b25  mov     rdx, [r15+10h]; h
0x180005b29  mov     rdi, rax
0x180005b2c  mov     rcx, cs:ghdcBits2; hdc
0x180005b33  call    cs:__imp_SelectObject
0x180005b39  mov     rcx, cs:ghdcBits2
0x180005b40  xor     r8d, r8d; y
0x180005b43  mov     edx, dword ptr [rbp+0C0h+pv+8]
0x180005b46  mov     rbx, rax
0x180005b49  mov     r9d, dword ptr [rsp+1C0h+pv+4]; cx
0x180005b4e  mov     [rsp+1C0h+rop], 0CC0020h; rop
0x180005b56  mov     [rsp+1C0h+y1], r13d; y1
0x180005b5b  mov     [rsp+1C0h+x1], r13d; x1
0x180005b60  mov     [rsp+1C0h+hdcSrc], rcx; hdcSrc
0x180005b65  mov     rcx, r12; hdc
0x180005b68  mov     dword ptr [rsp+1C0h+lpBits], edx; cy
0x180005b6c  xor     edx, edx; x
0x180005b6e  call    cs:__imp_BitBlt
0x180005b74  mov     rdx, rdi; h
0x180005b77  mov     rcx, r12; hdc
0x180005b7a  call    cs:__imp_SelectObject
0x180005b80  mov     rcx, cs:ghdcBits2; hdc
0x180005b87  mov     rdx, rbx; h
0x180005b8a  call    cs:__imp_SelectObject
0x180005b90  mov     rcx, r12; hdc
0x180005b93  call    cs:__imp_DeleteDC
0x180005b99  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180005ba0  call    cs:__imp_RtlLeaveCriticalSection
0x180005ba6  mov     edi, 1
0x180005bab  cmp     [r15], r13d
0x180005bae  jz      loc_180005CBE
0x180005bb4  lea     eax, [rdi+2]
0x180005bb7  mov     [rbp+0C0h+var_D0], ax
0x180005bbb  mov     eax, [rbp+0C0h+nWidth]
0x180005bbe  shr     eax, 1
0x180005bc0  mov     [rbp+0C0h+var_C4], ax
0x180005bc4  mov     eax, [rbp+0C0h+nHeight]
0x180005bc7  shr     eax, 2
0x180005bca  mov     [rbp+0C0h+var_C2], ax
0x180005bce  call    ?GetThreadDefCursorSize@@YAHXZ; GetThreadDefCursorSize(void)
0x180005bd3  mov     rdx, [rbp+0C0h+SourceString]; SourceString
0x180005bd7  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x180005bdb  xorps   xmm0, xmm0
0x180005bde  mov     qword ptr [rbp+0C0h+DestinationString.Length], r13
0x180005be2  mov     ebx, eax
0x180005be4  mov     [rbp+0C0h+DestinationString.Buffer], r13
0x180005be8  lea     rax, [rbp+0C0h+DestinationString]
0x180005bec  mov     [rbp+0C0h+var_110], r13
0x180005bf0  mov     [rbp+0C0h+var_118], rax
0x180005bf4  movups  xmmword ptr [rsp+1C0h+var_168.Length], xmm0
0x180005bf9  movups  [rsp+1C0h+var_158], xmm0
0x180005bfe  call    cs:__imp_RtlInitUnicodeString
0x180005c04  mov     rcx, [rbp+0C0h+var_E0]
0x180005c08  lea     r8, [rsp+1C0h+var_168]
0x180005c0d  mov     dword ptr [rsp+1C0h+var_158+8], r13d
0x180005c12  mov     qword ptr [rsp+1C0h+var_158], r8
0x180005c17  test    rcx, 0FFFFFFFFFFFF0000h
0x180005c1e  jnz     loc_180005D12
0x180005c24  mov     dword ptr [rsp+1C0h+var_168.Length], r13d
0x180005c29  mov     [rsp+1C0h+var_168.Buffer], rcx
0x180005c2e  mov     rdx, [rbp+0C0h+var_118]
0x180005c32  lea     r9, [rbp+0C0h+var_E0]
0x180005c36  mov     rcx, rsi
0x180005c39  mov     dword ptr [rsp+1C0h+lpBits], ebx
0x180005c3d  call    cs:__imp_NtUserSetCursorIconDataEx
0x180005c43  test    eax, eax
0x180005c45  jz      short loc_180005C91
0x180005c47  mov     rcx, [rbp+0C0h+h]
0x180005c4b  call    cs:__imp_GdiTrackHDelete
0x180005c51  mov     rcx, [rbp+0C0h+ho]
0x180005c55  call    cs:__imp_GdiTrackHDelete
0x180005c5b  cmp     [rbp+0C0h+var_D0], di
0x180005c5f  jz      short loc_180005CD5
0x180005c61  mov     rax, rsi
0x180005c64  mov     rcx, [rbp+0C0h+var_50]
0x180005c68  xor     rcx, rsp; StackCookie
0x180005c6b  call    __security_check_cookie
0x180005c70  add     rsp, 188h
0x180005c77  pop     r15
0x180005c79  pop     r14
0x180005c7b  pop     r13
0x180005c7d  pop     r12
0x180005c7f  pop     rdi
0x180005c80  pop     rsi
0x180005c81  pop     rbx
0x180005c82  pop     rbp
0x180005c83  retn
0x180005c84  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180005c8b  call    cs:__imp_RtlLeaveCriticalSection
0x180005c91  mov     rcx, [rbp+0C0h+h]; ho
0x180005c95  test    rcx, rcx
0x180005c98  jz      short loc_180005CA0
0x180005c9a  call    cs:__imp_DeleteObject
0x180005ca0  mov     rcx, [rbp+0C0h+ho]; ho
0x180005ca4  test    rcx, rcx
0x180005ca7  jz      short loc_180005CAF
0x180005ca9  call    cs:__imp_DeleteObject
0x180005caf  xor     edx, edx
0x180005cb1  mov     rcx, rsi
0x180005cb4  call    cs:__imp_NtUserDestroyCursor
0x180005cba  xor     eax, eax
0x180005cbc  jmp     short loc_180005C64
0x180005cbe  movzx   eax, word ptr [r15+4]
0x180005cc3  mov     [rbp+0C0h+var_C4], ax
0x180005cc7  movzx   eax, word ptr [r15+8]
0x180005ccc  mov     [rbp+0C0h+var_D0], di
0x180005cd0  jmp     loc_180005BCA
0x180005cd5  mov     rax, gs:30h
0x180005cde  mov     ecx, [rax+910h]
0x180005ce4  sub     ecx, edi
0x180005ce6  cmp     ecx, edi
0x180005ce8  jbe     loc_180005C61
0x180005cee  mov     eax, [rbp+0C0h+nHeight]
0x180005cf1  xor     r8d, r8d; unsigned __int16 *
0x180005cf4  mov     r9d, [rbp+0C0h+nWidth]; unsigned int
0x180005cf8  xor     edx, edx; HINSTANCE
0x180005cfa  shr     eax, 1
0x180005cfc  mov     rcx, rsi; HICON
0x180005cff  mov     dword ptr [rsp+1C0h+hdcSrc], r14d; unsigned int
0x180005d04  mov     dword ptr [rsp+1C0h+lpBits], eax; unsigned int
0x180005d08  call    ?CreateDpiCursors@@YAXPEAUHICON__@@PEAUHINSTANCE__@@PEBGKKK@Z; CreateDpiCursors(HICON__ *,HINSTANCE__ *,ushort const *,ulong,ulong,ulong)
0x180005d0d  jmp     loc_180005C61
0x180005d12  mov     rdx, rcx; SourceString
0x180005d15  lea     rcx, [rsp+1C0h+var_168]; DestinationString
0x180005d1a  call    cs:__imp_RtlInitUnicodeString
0x180005d20  mov     r8, qword ptr [rsp+1C0h+var_158]
0x180005d25  jmp     loc_180005C2E
0x180005d2a  mov     edx, dword ptr [rbp+0C0h+pv+8]
0x180005d2d  mov     [rbp+0C0h+nHeight], edx
0x180005d30  mov     [rbp+0C0h+var_90], r12d
0x180005d34  jmp     loc_180005AD4
0x180005d39  mov     [rbp+0C0h+ho], r13
0x180005d3d  jmp     loc_180005C91
```
