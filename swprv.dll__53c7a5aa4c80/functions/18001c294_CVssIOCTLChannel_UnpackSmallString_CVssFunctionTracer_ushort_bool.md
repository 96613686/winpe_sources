# CVssIOCTLChannel::UnpackSmallString(CVssFunctionTracer &,ushort * &,bool)

- ea: `0x18001c294`
- end: `0x18001c3fb`
- name: `?UnpackSmallString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG_N@Z`
- size: `359`
- prototype: `const unsigned __int16 *__fastcall(CVssIOCTLChannel *__hidden this, struct CVssFunctionTracer *, unsigned __int16 **, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b380`
- `0x18001b65c`

## callees

- `0x18000212c`
- `0x18000d6bc`
- `0x1800171dc`
- `0x18001c294`
- `0x18003649c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c360`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c360`

## pseudocode

```c
const unsigned __int16 *__fastcall CVssIOCTLChannel::UnpackSmallString(
        CVssIOCTLChannel *this,
        struct CVssFunctionTracer *a2,
        LPVOID *a3,
        char a4)
{
  LPVOID *v4; // rbx
  struct CVssFunctionTracer *v5; // rsi
  unsigned int *v7; // r14
  unsigned __int16 v8; // r15
  unsigned __int16 *v9; // rax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+20h] [rbp-128h]
  char *v13; // [rsp+40h] [rbp-108h]
  unsigned int v15; // [rsp+48h] [rbp-100h] BYREF
  _com_error *v16; // [rsp+50h] [rbp-F8h] BYREF
  const std::exception *v17; // [rsp+58h] [rbp-F0h] BYREF
  _QWORD v18[3]; // [rsp+60h] [rbp-E8h] BYREF
  int v19; // [rsp+78h] [rbp-D0h]
  int v20; // [rsp+7Ch] [rbp-CCh]
  int v21; // [rsp+80h] [rbp-C8h]
  char v22[120]; // [rsp+88h] [rbp-C0h] BYREF
  int v23; // [rsp+100h] [rbp-48h]
  unsigned __int16 v28; // [rsp+168h] [rbp+20h] BYREF

  LOBYTE(v28) = a4;
  v4 = a3;
  v5 = a2;
  v7 = (unsigned int *)((char *)a2 + 8);
  v13 = (char *)a2 + 8;
  *((_DWORD *)a2 + 2) = 0;
  CoTaskMemFree(*a3);
  *v4 = 0;
  *v7 = 0;
  v28 = 0;
  try
  {
    CVssIOCTLChannel::Unpack<unsigned short>(this, v5, &v28, 1u);
    v8 = v28 >> 1;
    if ( v28 >> 1 )
    {
      v9 = VssAllocString(v5, v8);
      *v4 = v9;
      CVssIOCTLChannel::Unpack<unsigned short>(this, v5, v9, v8);
      *((_WORD *)*v4 + v8) = 0;
    }
  }
  catch ( long v15 )
  {
    CVssFunctionTracer::HandleHresultException(
      a2,
      v15,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackSmallString",
      0x39Fu,
      *((_DWORD *)a2 + 9));
    v7 = (unsigned int *)v13;
    v5 = a2;
    v4 = a3;
  }
  catch ( _com_error *v16 )
  {
    CVssFunctionTracer::HandleComException(
      a2,
      v16,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackSmallString",
      0x39Fu,
      *((_DWORD *)a2 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      a2,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackSmallString",
      0x39Fu,
      *((_DWORD *)a2 + 9));
    v7 = (unsigned int *)v13;
    v5 = a2;
    v4 = a3;
  }
  catch ( const std::exception *v17 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      a2,
      v17,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackSmallString",
      0x39Fu,
      *((_DWORD *)a2 + 9));
  }
  if ( (*v7 & 0x80000000) != 0 )
  {
    CoTaskMemFree(*v4);
    *v4 = 0;
    v10 = *v7;
    v18[0] = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v18[1] = L"CVssIOCTLChannel::UnpackSmallString";
    v18[2] = L"INCICHLH";
    v19 = 932;
    v20 = 10;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    v12 = v10;
    CVssFunctionTracer::Throw(v5, v18, v10, L"Exception re-thrown 0x%08lx", v12);
  }
  return (const unsigned __int16 *)*v4;
}

```

## disassembly

```asm
0x18001c294  mov     byte ptr [rsp+arg_18], r9b
0x18001c299  mov     [rsp+arg_10], r8
0x18001c29e  mov     [rsp+arg_8], rdx
0x18001c2a3  push    rbx
0x18001c2a4  push    rsi
0x18001c2a5  push    rdi
0x18001c2a6  push    r12
0x18001c2a8  push    r13
0x18001c2aa  push    r14
0x18001c2ac  push    r15
0x18001c2ae  sub     rsp, 110h
0x18001c2b5  mov     rbx, r8
0x18001c2b8  mov     rsi, rdx
0x18001c2bb  mov     r13, rcx
0x18001c2be  lea     r14, [rdx+8]
0x18001c2c2  mov     [rsp+148h+var_108], r14
0x18001c2c7  xor     edi, edi
0x18001c2c9  mov     [r14], edi
0x18001c2cc  mov     rcx, [r8]; pv
0x18001c2cf  call    cs:__imp_CoTaskMemFree
0x18001c2d5  mov     [rbx], rdi
0x18001c2d8  mov     [r14], edi
0x18001c2db  mov     [rsp+148h+arg_18], di
0x18001c2e3  lea     r9d, [rdi+1]
0x18001c2e7  lea     r8, [rsp+148h+arg_18]; void *
0x18001c2ef  mov     rdx, rsi; struct CVssFunctionTracer *
0x18001c2f2  mov     rcx, r13; this
0x18001c2f5  call    ??$Unpack@G@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAGK_N@Z; CVssIOCTLChannel::Unpack<ushort>(CVssFunctionTracer &,ushort *,ulong,bool)
0x18001c2fa  movzx   r15d, [rsp+148h+arg_18]
0x18001c303  shr     r15w, 1
0x18001c307  jz      short loc_18001C335
0x18001c309  movzx   r12d, r15w
0x18001c30d  mov     edx, r12d; unsigned __int64
0x18001c310  mov     rcx, rsi; struct CVssFunctionTracer *
0x18001c313  call    ?VssAllocString@@YAPEAGAEAVCVssFunctionTracer@@_K@Z; VssAllocString(CVssFunctionTracer &,unsigned __int64)
0x18001c318  mov     [rbx], rax
0x18001c31b  movzx   r9d, r15w
0x18001c31f  mov     r8, rax; void *
0x18001c322  mov     rdx, rsi; struct CVssFunctionTracer *
0x18001c325  mov     rcx, r13; this
0x18001c328  call    ??$Unpack@G@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAGK_N@Z; CVssIOCTLChannel::Unpack<ushort>(CVssFunctionTracer &,ushort *,ulong,bool)
0x18001c32d  mov     rax, [rbx]
0x18001c330  mov     [rax+r12*2], di
0x18001c335  jmp     short loc_18001C354
0x18001c337  jmp     short loc_18001C33D
0x18001c339  jmp     short loc_18001C33D
0x18001c33b  jmp     short $+2
0x18001c33d  mov     r14, [rsp+148h+var_108]
0x18001c342  mov     rsi, [rsp+148h+arg_8]
0x18001c34a  mov     rbx, [rsp+148h+arg_10]
0x18001c352  xor     edi, edi
0x18001c354  cmp     [r14], edi
0x18001c357  jge     loc_18001C3E5
0x18001c35d  mov     rcx, [rbx]; pv
0x18001c360  call    cs:__imp_CoTaskMemFree
0x18001c366  mov     [rbx], rdi
0x18001c369  mov     ebx, [r14]
0x18001c36c  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x18001c373  mov     [rsp+148h+var_E8], rax
0x18001c378  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::UnpackSmallString"
0x18001c37f  mov     [rsp+148h+var_E0], rax
0x18001c384  lea     rax, aIncichlh; "INCICHLH"
0x18001c38b  mov     [rsp+148h+var_D8], rax
0x18001c390  mov     [rsp+148h+var_D0], 3A4h
0x18001c398  mov     [rsp+148h+var_CC], 0Ah
0x18001c3a0  mov     [rsp+148h+var_C8], 0FFh
0x18001c3ab  mov     [rsp+148h+var_48], 1000000h
0x18001c3b6  xor     edx, edx; Val
0x18001c3b8  lea     r8d, [rdx+78h]; Size
0x18001c3bc  lea     rcx, [rsp+148h+var_C0]; void *
0x18001c3c4  call    memset_0
0x18001c3c9  mov     [rsp+148h+var_128], ebx
0x18001c3cd  lea     r9, aExceptionReThr; "Exception re-thrown 0x%08lx"
0x18001c3d4  mov     r8d, ebx
0x18001c3d7  lea     rdx, [rsp+148h+var_E8]
0x18001c3dc  mov     rcx, rsi
0x18001c3df  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001c3e5  mov     rax, [rbx]
0x18001c3e8  add     rsp, 110h
0x18001c3ef  pop     r15
0x18001c3f1  pop     r14
0x18001c3f3  pop     r13
0x18001c3f5  pop     r12
0x18001c3f7  pop     rdi
0x18001c3f8  pop     rsi
0x18001c3f9  pop     rbx
0x18001c3fa  retn
```
