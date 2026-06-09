# CallRpcSPM

- ea: `0x180008180`
- end: `0x180008418`
- name: `CallRpcSPM`
- size: `664`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007f6c`
- `0x1800080c0`
- `0x1800095f0`

## callees

- `0x180008180`
- `0x180022047`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180008230`
- `ntdll!NtQueryInformationThread` at `0x180008230`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002232e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002232e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800082d2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800082d2`
- `RPCRT4!NdrClientCall3` at `0x1800082bc`
- `RPCRT4!NdrClientCall3` at `0x1800082bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008314`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008314`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008387`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008387`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008264`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008264`

## pseudocode

```c
__int64 __fastcall CallRpcSPM(__int64 a1, __int64 a2, unsigned int a3, void *a4)
{
  void *v8; // rdi
  NTSTATUS Pointer; // ebx
  int v10; // eax
  CLIENT_CALL_RETURN v11; // rax
  unsigned int v12; // eax
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rbx
  _QWORD *Value; // rax
  int v18; // eax
  __int64 **v19; // r9
  __int64 *v20; // r8
  __int64 *i; // r10
  size_t Size; // [rsp+50h] [rbp-108h] BYREF
  void *Src; // [rsp+58h] [rbp-100h] BYREF
  int v24; // [rsp+60h] [rbp-F8h]
  CLIENT_CALL_RETURN v25; // [rsp+68h] [rbp-F0h]
  __int64 v26; // [rsp+70h] [rbp-E8h]
  void *v27; // [rsp+80h] [rbp-D8h]
  __int128 v28; // [rsp+90h] [rbp-C8h] BYREF
  _OWORD v29[3]; // [rsp+A0h] [rbp-B8h] BYREF
  __int128 ThreadInformation; // [rsp+D0h] [rbp-88h] BYREF
  __int128 v31; // [rsp+E0h] [rbp-78h]
  __int128 v32; // [rsp+F0h] [rbp-68h]
  GUID ActivityId; // [rsp+100h] [rbp-58h] BYREF

  v26 = a2;
  v27 = a4;
  v8 = 0;
  LODWORD(Size) = 0;
  Src = 0;
  memset(v29, 0, sizeof(v29));
  ThreadInformation = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  if ( !a1 )
  {
    Pointer = -1073741504;
    goto LABEL_8;
  }
  Pointer = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( Pointer < 0 )
    goto LABEL_7;
  *(_OWORD *)(a2 + 8) = v31;
  ActivityId = 0;
  EventActivityIdControl(1u, &ActivityId);
  v10 = *(__int16 *)(a2 + 2);
  v25.Simple = 0;
  v11.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                  0x12u,
                  0,
                  a1,
                  &ActivityId,
                  v10,
                  a2,
                  &Size,
                  &Src,
                  v29).Pointer;
  Pointer = (NTSTATUS)v11.Pointer;
  v25.Pointer = v11.Pointer;
  v24 = (int)v11.Pointer;
  if ( SLODWORD(v11.Simple) < 0 )
    goto LABEL_7;
  v12 = Size;
  if ( (unsigned int)Size > a3 )
  {
    Pointer = -1073741789;
LABEL_7:
    v8 = Src;
    goto LABEL_8;
  }
  if ( LODWORD(v29[0]) )
  {
    if ( *(_DWORD *)(a2 + 40) == 17 )
    {
      *((_QWORD *)&v28 + 1) = *((_QWORD *)Src + 11);
      LODWORD(v28) = 8;
    }
    v14 = *(_QWORD *)&v29[1];
    v15 = *((_QWORD *)&v29[0] + 1);
    v16 = LODWORD(v29[0]);
    Value = TlsGetValue(SecTlsPackage);
    if ( Value )
    {
      v19 = (__int64 **)(Value[26] + 16LL);
      v20 = *v19;
      for ( i = 0; v20 != (__int64 *)v19; v20 = (__int64 *)*v20 )
      {
        i = v20;
        if ( *((_DWORD *)v20 + 4) == v16 )
          break;
        i = 0;
      }
      if ( i )
        v18 = ((__int64 (__fastcall *)(__int64, __int64, char *, __int128 *))i[3])(v15, v14, (char *)&v29[1] + 8, &v28);
      else
        v18 = -1073741511;
    }
    else
    {
      v18 = -1073741811;
    }
    Pointer = v18;
    if ( v18 < 0 )
      goto LABEL_7;
    v12 = Size;
  }
  v8 = Src;
  memcpy_0(a4, Src, v12);
LABEL_8:
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180008180  mov     r11, rsp
0x180008183  mov     [r11+18h], r8d
0x180008187  push    rbx
0x180008188  push    rsi
0x180008189  push    rdi
0x18000818a  push    r12
0x18000818c  push    r14
0x18000818e  push    r15
0x180008190  sub     rsp, 128h
0x180008197  mov     rax, cs:__security_cookie
0x18000819e  xor     rax, rsp
0x1800081a1  mov     [rsp+158h+var_48], rax
0x1800081a9  mov     r15, r9
0x1800081ac  mov     r14d, r8d
0x1800081af  mov     rsi, rdx
0x1800081b2  mov     r12, rcx
0x1800081b5  mov     [rsp+158h+var_E8], rdx
0x1800081ba  mov     [rsp+158h+var_D8], r9
0x1800081c2  xor     edi, edi
0x1800081c4  mov     dword ptr [rsp+158h+Size], edi
0x1800081c8  mov     [rsp+158h+Src], rdi
0x1800081cd  xorps   xmm0, xmm0
0x1800081d0  movups  [rsp+158h+var_B8], xmm0
0x1800081d8  movups  [rsp+158h+var_A8], xmm0
0x1800081e0  movups  [rsp+158h+var_98], xmm0
0x1800081e8  xorps   xmm1, xmm1
0x1800081eb  movups  [rsp+158h+ThreadInformation], xmm1
0x1800081f3  movups  xmmword ptr [r11-78h], xmm1
0x1800081f8  movups  xmmword ptr [r11-68h], xmm1
0x1800081fd  movups  [rsp+158h+var_C8], xmm0
0x180008205  test    rcx, rcx
0x180008208  jnz     short loc_180008214
0x18000820a  mov     ebx, 0C0000140h
0x18000820f  jmp     loc_18000830C
0x180008214  mov     [rsp+158h+ReturnLength], rdi; ReturnLength
0x180008219  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18000821f  lea     r8, [rsp+158h+ThreadInformation]; ThreadInformation
0x180008227  xor     edx, edx; ThreadInformationClass
0x180008229  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180008230  call    cs:__imp_NtQueryInformationThread
0x180008236  mov     ebx, eax
0x180008238  test    eax, eax
0x18000823a  js      loc_180008307
0x180008240  movups  xmm0, [rsp+158h+var_78]
0x180008248  movups  xmmword ptr [rsi+8], xmm0
0x18000824c  xorps   xmm0, xmm0
0x18000824f  movups  xmmword ptr [rsp+158h+ActivityId.Data1], xmm0
0x180008257  lea     rdx, [rsp+158h+ActivityId]; ActivityId
0x18000825f  mov     ecx, 1; ControlCode
0x180008264  call    cs:__imp_EventActivityIdControl
0x18000826a  movsx   eax, word ptr [rsi+2]
0x18000826e  mov     [rsp+158h+var_F0], rdi
0x180008273  lea     rcx, [rsp+158h+var_B8]
0x18000827b  mov     [rsp+158h+var_110], rcx
0x180008280  lea     rcx, [rsp+158h+Src]
0x180008285  mov     [rsp+158h+var_118], rcx
0x18000828a  lea     rcx, [rsp+158h+Size]
0x18000828f  mov     [rsp+158h+var_120], rcx
0x180008294  mov     [rsp+158h+var_128], rsi
0x180008299  mov     [rsp+158h+var_130], eax
0x18000829d  lea     rax, [rsp+158h+ActivityId]
0x1800082a5  mov     [rsp+158h+ReturnLength], rax
0x1800082aa  mov     r9, r12
0x1800082ad  xor     r8d, r8d; pReturnValue
0x1800082b0  mov     edx, 12h; nProcNum
0x1800082b5  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800082bc  call    cs:__imp_NdrClientCall3
0x1800082c2  mov     rbx, rax
0x1800082c5  mov     [rsp+158h+var_F0], rax
0x1800082ca  mov     [rsp+158h+var_F8], eax
0x1800082ce  jmp     short loc_1800082F5
0x1800082d0  mov     ecx, eax; Status
0x1800082d2  call    cs:__imp_I_RpcMapWin32Status
0x1800082d8  mov     ebx, eax
0x1800082da  mov     [rsp+158h+var_F8], eax
0x1800082de  xor     edi, edi
0x1800082e0  mov     r14d, [rsp+158h+arg_10]
0x1800082e8  mov     rsi, [rsp+158h+var_E8]
0x1800082ed  mov     r15, [rsp+158h+var_D8]
0x1800082f5  test    ebx, ebx
0x1800082f7  js      short loc_180008307
0x1800082f9  mov     eax, dword ptr [rsp+158h+Size]
0x1800082fd  cmp     eax, r14d
0x180008300  jbe     short loc_18000833D
0x180008302  mov     ebx, 0C0000023h
0x180008307  mov     rdi, [rsp+158h+Src]
0x18000830c  test    rdi, rdi
0x18000830f  jz      short loc_18000831A
0x180008311  mov     rcx, rdi; hMem
0x180008314  call    cs:__imp_LocalFree
0x18000831a  mov     eax, ebx
0x18000831c  mov     rcx, [rsp+158h+var_48]
0x180008324  xor     rcx, rsp; StackCookie
0x180008327  call    __security_check_cookie
0x18000832c  add     rsp, 128h
0x180008333  pop     r15
0x180008335  pop     r14
0x180008337  pop     r12
0x180008339  pop     rdi
0x18000833a  pop     rsi
0x18000833b  pop     rbx
0x18000833c  retn
0x18000833d  mov     edx, dword ptr [rsp+158h+var_B8]
0x180008344  test    edx, edx
0x180008346  jz      loc_180008400
0x18000834c  cmp     dword ptr [rsi+28h], 11h
0x180008350  jnz     short loc_18000836E
0x180008352  mov     rax, [rsp+158h+Src]
0x180008357  mov     rcx, [rax+58h]
0x18000835b  mov     qword ptr [rsp+158h+var_C8+8], rcx
0x180008363  mov     dword ptr [rsp+158h+var_C8], 8
0x18000836e  mov     rsi, qword ptr [rsp+158h+var_A8]
0x180008376  mov     r14, qword ptr [rsp+158h+var_B8+8]
0x18000837e  mov     rbx, rdx
0x180008381  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180008387  call    cs:__imp_TlsGetValue
0x18000838d  test    rax, rax
0x180008390  jnz     short loc_180008399
0x180008392  mov     eax, 0C000000Dh
0x180008397  jmp     short loc_1800083F2
0x180008399  mov     r9, [rax+0D0h]
0x1800083a0  add     r9, 10h
0x1800083a4  mov     r8, [r9]
0x1800083a7  mov     r10, rdi
0x1800083aa  cmp     r8, r9
0x1800083ad  jz      short loc_1800083C7
0x1800083af  nop
0x1800083b0  mov     r10, r8
0x1800083b3  mov     eax, [r8+10h]
0x1800083b7  cmp     rax, rbx
0x1800083ba  jz      short loc_1800083C7
0x1800083bc  mov     r10, rdi
0x1800083bf  mov     r8, [r8]
0x1800083c2  cmp     r8, r9
0x1800083c5  jnz     short loc_1800083B0
0x1800083c7  test    r10, r10
0x1800083ca  jz      short loc_1800083ED
0x1800083cc  lea     r9, [rsp+158h+var_C8]
0x1800083d4  lea     r8, [rsp+158h+var_A8+8]
0x1800083dc  mov     rdx, rsi
0x1800083df  mov     rcx, r14
0x1800083e2  mov     rax, [r10+18h]
0x1800083e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083eb  jmp     short loc_1800083F2
0x1800083ed  mov     eax, 0C0000139h
0x1800083f2  mov     ebx, eax
0x1800083f4  test    eax, eax
0x1800083f6  js      loc_180008307
0x1800083fc  mov     eax, dword ptr [rsp+158h+Size]
0x180008400  mov     r8d, eax; Size
0x180008403  mov     rdi, [rsp+158h+Src]
0x180008408  mov     rdx, rdi; Src
0x18000840b  mov     rcx, r15; void *
0x18000840e  call    memcpy_0
0x180008413  jmp     loc_18000830C
0x180022320  push    rbp
0x180022322  sub     rsp, 50h
0x180022326  mov     rbp, rdx
0x180022329  mov     rcx, [rcx]
0x18002232c  mov     ecx, [rcx]; ExceptionCode
0x18002232e  call    cs:__imp_I_RpcExceptionFilter
0x180022334  nop
0x180022335  add     rsp, 50h
0x180022339  pop     rbp
0x18002233a  retn
```
