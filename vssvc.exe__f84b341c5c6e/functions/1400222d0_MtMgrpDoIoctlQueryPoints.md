# MtMgrpDoIoctlQueryPoints

- ea: `0x1400222d0`
- end: `0x140022620`
- name: `MtMgrpDoIoctlQueryPoints`
- size: `848`
- prototype: `__int64 __fastcall(HANDLE hDevice, void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140021cd8`

## callees

- `0x1400222d0`
- `0x140025abc`
- `0x140091560`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400224b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400224b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022583`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400223d8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140022579`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400223d8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140022579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400223fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022406`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400223fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022406`

## pseudocode

```c
__int64 __fastcall MtMgrpDoIoctlQueryPoints(HANDLE hDevice, _WORD *Src, __int64 a3, _QWORD *a4)
{
  _WORD *v5; // rdi
  _DWORD *v7; // rsi
  void *lpOutBuffer; // r15
  __int64 v9; // rbx
  __int64 v10; // rax
  bool v11; // zf
  DWORD v12; // r14d
  _DWORD *v13; // rax
  DWORD v14; // ebx
  DWORD LastError; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v17; // rcx
  int v18; // edx
  const char *v19; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-68h] BYREF
  _OWORD OutBuffer[2]; // [rsp+48h] [rbp-60h] BYREF

  v5 = Src;
  v7 = 0;
  lpOutBuffer = 0;
  BytesReturned = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( a4 )
  {
    if ( Src )
    {
      v9 = -1;
      v10 = -1;
      do
        v11 = Src[++v10] == 0;
      while ( !v11 );
      v12 = 2 * v10 + 24;
      v13 = CoTaskMemAlloc(v12);
      v7 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, v12);
        do
          v11 = v5[++v9] == 0;
        while ( !v11 );
        v7[4] = 24;
        *((_WORD *)v7 + 10) = 2 * v9;
        memcpy_0(v7 + 6, v5, (unsigned int)(2 * v9));
        if ( DeviceIoControl(hDevice, 0x6D0008u, v7, v12, OutBuffer, 0x20u, &BytesReturned, 0) )
        {
          LODWORD(v5) = 1;
          v14 = 0;
          goto LABEL_10;
        }
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError == 234 || LastError == 122 || LastError == 24 )
        {
          lpOutBuffer = ASR_ALLOC(LODWORD(OutBuffer[0]));
          if ( lpOutBuffer )
          {
            if ( DeviceIoControl(hDevice, 0x6D0008u, v7, v12, lpOutBuffer, OutBuffer[0], &BytesReturned, 0) )
            {
              v14 = 0;
              *a4 = lpOutBuffer;
              lpOutBuffer = 0;
              LODWORD(v5) = 1;
              goto LABEL_10;
            }
            v14 = GetLastError();
            LODWORD(v5) = 0;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v18 = 15;
              v19 = "dwIoctlLastError";
              goto LABEL_36;
            }
          }
          else
          {
            LODWORD(v5) = 0;
            v14 = 14;
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              WPP_SF_Ds(
                *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                14,
                (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
                14,
                "pQueryPointOutput");
            }
          }
        }
        else
        {
          LODWORD(v5) = 0;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v18 = 13;
            v19 = "dwIoctlLastError";
LABEL_36:
            WPP_SF_Ds(
              *(_QWORD *)v17->Gpt.DiskId.Data4,
              v18,
              (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
              v14,
              v19);
          }
        }
      }
      else
      {
        LODWORD(v5) = 0;
        v14 = 14;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v18 = 12;
          v19 = "pQueryPointInput";
          goto LABEL_36;
        }
      }
    }
    else
    {
      v14 = 87;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          11,
          (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
          87,
          "pwszNameToQuery");
      }
    }
  }
  else
  {
    LODWORD(v5) = 0;
    v14 = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        10,
        (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
        87,
        "ppOutQueryPointOutput");
    }
  }
LABEL_10:
  CoTaskMemFree(v7);
  CoTaskMemFree(lpOutBuffer);
  SetLastError(v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400222d0  push    rbx
0x1400222d2  push    rsi
0x1400222d3  push    rdi
0x1400222d4  push    r12
0x1400222d6  push    r13
0x1400222d8  push    r15
0x1400222da  sub     rsp, 78h
0x1400222de  mov     rax, cs:__security_cookie
0x1400222e5  xor     rax, rsp
0x1400222e8  mov     [rsp+0A8h+var_40], rax
0x1400222ed  mov     r12, r9
0x1400222f0  mov     rdi, rdx
0x1400222f3  mov     r13, rcx
0x1400222f6  nop     word ptr [rax+rax+00000000h]
0x140022300  xor     esi, esi
0x140022302  xorps   xmm0, xmm0
0x140022305  xor     r15d, r15d
0x140022308  mov     [rsp+0A8h+BytesReturned], esi
0x14002230c  movups  [rsp+0A8h+OutBuffer], xmm0
0x140022311  movups  [rsp+0A8h+var_50], xmm0
0x140022316  test    r9, r9
0x140022319  jz      loc_140022435
0x14002231f  test    rdi, rdi
0x140022322  jz      loc_14002248C
0x140022328  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14002232f  mov     [rsp+0A8h+arg_10], rbp
0x140022337  mov     rax, rbx
0x14002233a  mov     [rsp+0A8h+var_38], r14
0x14002233f  nop
0x140022340  cmp     [rdx+rax*2+2], si
0x140022345  lea     rax, [rax+1]
0x140022349  jnz     short loc_140022340
0x14002234b  lea     r14d, ds:18h[rax*2]
0x140022353  mov     ecx, r14d; cb
0x140022356  mov     ebp, r14d
0x140022359  call    cs:__imp_CoTaskMemAlloc
0x14002235f  mov     rsi, rax
0x140022362  test    rax, rax
0x140022365  jz      loc_1400225CF
0x14002236b  mov     r8d, ebp; Size
0x14002236e  xor     edx, edx; Val
0x140022370  mov     rcx, rax; void *
0x140022373  call    memset_0
0x140022378  nop     dword ptr [rax+rax+00000000h]
0x140022380  cmp     [rdi+rbx*2+2], r15w
0x140022386  lea     rbx, [rbx+1]
0x14002238a  jnz     short loc_140022380
0x14002238c  lea     eax, [rbx+rbx]
0x14002238f  mov     dword ptr [rsi+10h], 18h
0x140022396  mov     r8d, eax; Size
0x140022399  lea     rcx, [rsi+18h]; void *
0x14002239d  mov     rdx, rdi; Src
0x1400223a0  mov     [rsi+14h], ax
0x1400223a4  call    memcpy_0
0x1400223a9  mov     [rsp+0A8h+lpOverlapped], r15; lpOverlapped
0x1400223ae  lea     rax, [rsp+0A8h+BytesReturned]
0x1400223b3  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x1400223b8  mov     r9d, r14d; nInBufferSize
0x1400223bb  lea     rax, [rsp+0A8h+OutBuffer]
0x1400223c0  mov     [rsp+0A8h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x1400223c8  mov     r8, rsi; lpInBuffer
0x1400223cb  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x1400223d0  mov     edx, 6D0008h; dwIoControlCode
0x1400223d5  mov     rcx, r13; hDevice
0x1400223d8  call    cs:__imp_DeviceIoControl
0x1400223de  test    eax, eax
0x1400223e0  jz      loc_1400224B4
0x1400223e6  mov     edi, 1
0x1400223eb  xor     ebx, ebx
0x1400223ed  mov     rbp, [rsp+0A8h+arg_10]
0x1400223f5  mov     r14, [rsp+0A8h+var_38]
0x1400223fa  mov     rcx, rsi; pv
0x1400223fd  call    cs:__imp_CoTaskMemFree
0x140022403  mov     rcx, r15; pv
0x140022406  call    cs:__imp_CoTaskMemFree
0x14002240c  nop     dword ptr [rax+00h]
0x140022410  mov     ecx, ebx; dwErrCode
0x140022412  call    cs:__imp_SetLastError
0x140022418  mov     eax, edi
0x14002241a  mov     rcx, [rsp+0A8h+var_40]
0x14002241f  xor     rcx, rsp; StackCookie
0x140022422  call    __security_check_cookie
0x140022427  add     rsp, 78h
0x14002242b  pop     r15
0x14002242d  pop     r13
0x14002242f  pop     r12
0x140022431  pop     rdi
0x140022432  pop     rsi
0x140022433  pop     rbx
0x140022434  retn
0x140022435  xor     edi, edi
0x140022437  mov     ebx, 57h ; 'W'
0x14002243c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022443  lea     rax, WPP_GLOBAL_Control
0x14002244a  cmp     rcx, rax
0x14002244d  jz      short loc_1400223FA
0x14002244f  test    byte ptr [rcx+1Ch], 8
0x140022453  jz      short loc_1400223FA
0x140022455  mov     edx, 0Ah
0x14002245a  lea     rax, aPpoutquerypoin; "ppOutQueryPointOutput"
0x140022461  jmp     short loc_14002246F
0x140022463  mov     edx, 0Bh
0x140022468  lea     rax, aPwsznametoquer; "pwszNameToQuery"
0x14002246f  mov     rcx, [rcx+10h]
0x140022473  lea     r8, WPP_78d403bd48723deb5f738664aa5853e8_Traceguids
0x14002247a  mov     r9d, ebx
0x14002247d  mov     [rsp+0A8h+lpOutBuffer], rax
0x140022482  call    WPP_SF_Ds
0x140022487  jmp     loc_1400223FA
0x14002248c  mov     ebx, 57h ; 'W'
0x140022491  mov     rcx, cs:WPP_GLOBAL_Control
0x140022498  lea     rax, WPP_GLOBAL_Control
0x14002249f  cmp     rcx, rax
0x1400224a2  jz      loc_1400223FA
0x1400224a8  test    byte ptr [rcx+1Ch], 8
0x1400224ac  jz      loc_1400223FA
0x1400224b2  jmp     short loc_140022463
0x1400224b4  call    cs:__imp_GetLastError
0x1400224ba  mov     ebx, eax
0x1400224bc  cmp     eax, 0EAh
0x1400224c1  jz      short loc_140022501
0x1400224c3  cmp     eax, 7Ah ; 'z'
0x1400224c6  jz      short loc_140022501
0x1400224c8  cmp     eax, 18h
0x1400224cb  jz      short loc_140022501
0x1400224cd  xor     edi, edi
0x1400224cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400224d6  lea     rax, WPP_GLOBAL_Control
0x1400224dd  cmp     rcx, rax
0x1400224e0  jz      loc_1400223ED
0x1400224e6  test    byte ptr [rcx+1Ch], 8
0x1400224ea  jz      loc_1400223ED
0x1400224f0  mov     edx, 0Dh
0x1400224f5  lea     rax, aDwioctllasterr; "dwIoctlLastError"
0x1400224fc  jmp     loc_140022603
0x140022501  mov     ecx, dword ptr [rsp+0A8h+OutBuffer]; Size
0x140022505  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14002250a  mov     r15, rax
0x14002250d  test    rax, rax
0x140022510  jnz     short loc_14002254B
0x140022512  xor     edi, edi
0x140022514  mov     ebx, 0Eh
0x140022519  mov     rcx, cs:WPP_GLOBAL_Control
0x140022520  lea     rax, WPP_GLOBAL_Control
0x140022527  cmp     rcx, rax
0x14002252a  jz      loc_1400223ED
0x140022530  test    byte ptr [rcx+1Ch], 8
0x140022534  jz      loc_1400223ED
0x14002253a  mov     edx, ebx
0x14002253c  lea     rax, aPquerypointout; "pQueryPointOutput"
0x140022543  mov     r9d, ebx
0x140022546  jmp     loc_140022606
0x14002254b  lea     rax, [rsp+0A8h+BytesReturned]
0x140022550  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x140022559  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x14002255e  mov     r9d, r14d; nInBufferSize
0x140022561  mov     eax, dword ptr [rsp+0A8h+OutBuffer]
0x140022565  mov     r8, rsi; lpInBuffer
0x140022568  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x14002256c  mov     edx, 6D0008h; dwIoControlCode
0x140022571  mov     rcx, r13; hDevice
0x140022574  mov     [rsp+0A8h+lpOutBuffer], r15; lpOutBuffer
0x140022579  call    cs:__imp_DeviceIoControl
0x14002257f  test    eax, eax
0x140022581  jnz     short loc_1400225BC
0x140022583  call    cs:__imp_GetLastError
0x140022589  mov     ebx, eax
0x14002258b  xor     edi, edi
0x14002258d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022594  lea     rax, WPP_GLOBAL_Control
0x14002259b  cmp     rcx, rax
0x14002259e  jz      loc_1400223ED
0x1400225a4  test    byte ptr [rcx+1Ch], 8
0x1400225a8  jz      loc_1400223ED
0x1400225ae  mov     edx, 0Fh
0x1400225b3  lea     rax, aDwioctllasterr; "dwIoctlLastError"
0x1400225ba  jmp     short loc_140022603
0x1400225bc  xor     ebx, ebx
0x1400225be  mov     [r12], r15
0x1400225c2  xor     r15d, r15d
0x1400225c5  mov     edi, 1
0x1400225ca  jmp     loc_1400223ED
0x1400225cf  xor     edi, edi
0x1400225d1  mov     ebx, 0Eh
0x1400225d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400225dd  lea     rax, WPP_GLOBAL_Control
0x1400225e4  cmp     rcx, rax
0x1400225e7  jz      loc_1400223ED
0x1400225ed  test    byte ptr [rcx+1Ch], 8
0x1400225f1  jz      loc_1400223ED
0x1400225f7  mov     edx, 0Ch
0x1400225fc  lea     rax, aPquerypointinp; "pQueryPointInput"
0x140022603  mov     r9d, ebx
0x140022606  mov     rcx, [rcx+10h]
0x14002260a  lea     r8, WPP_78d403bd48723deb5f738664aa5853e8_Traceguids
0x140022611  mov     [rsp+0A8h+lpOutBuffer], rax
0x140022616  call    WPP_SF_Ds
0x14002261b  jmp     loc_1400223ED
```
