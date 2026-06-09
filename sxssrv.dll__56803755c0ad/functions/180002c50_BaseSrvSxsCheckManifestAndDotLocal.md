# BaseSrvSxsCheckManifestAndDotLocal

- ea: `0x180002c50`
- end: `0x180003167`
- name: `BaseSrvSxsCheckManifestAndDotLocal`
- size: `1303`
- prototype: `__int64 __fastcall(unsigned __int16 *, USHORT *, __int64, int, _QWORD *, int, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002800`

## callees

- `0x180002c50`
- `0x180003e70`
- `0x1800040f0`
- `0x180004150`
- `0x180005830`
- `0x1800060c0`
- `0x180006a2c`
- `0x180006c07`
- `0x180006c13`
- `0x180006c30`
- `0x180007010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002f82`
- `ntdll!RtlFreeHeap` at `0x180002fa5`
- `ntdll!RtlFreeHeap` at `0x180002f82`
- `ntdll!RtlFreeHeap` at `0x180002fa5`
- `ntdll!RtlAllocateHeap` at `0x180002f08`
- `ntdll!RtlAllocateHeap` at `0x180003000`
- `ntdll!RtlAllocateHeap` at `0x180002f08`
- `ntdll!RtlAllocateHeap` at `0x180003000`
- `ntdll!RtlAppendUnicodeToString` at `0x180002f46`
- `ntdll!RtlAppendUnicodeToString` at `0x18000303f`
- `ntdll!RtlAppendUnicodeToString` at `0x180002f46`
- `ntdll!RtlAppendUnicodeToString` at `0x18000303f`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002d3d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002d3d`
- `CSRSRV!CsrRevertToSelf` at `0x180002e4c`
- `CSRSRV!CsrRevertToSelf` at `0x180003088`
- `CSRSRV!CsrRevertToSelf` at `0x18000311e`
- `CSRSRV!CsrRevertToSelf` at `0x180002e4c`
- `CSRSRV!CsrRevertToSelf` at `0x180003088`
- `CSRSRV!CsrRevertToSelf` at `0x18000311e`
- `CSRSRV!CsrImpersonateClient` at `0x180002e0f`
- `CSRSRV!CsrImpersonateClient` at `0x180002e99`
- `CSRSRV!CsrImpersonateClient` at `0x180003057`
- `CSRSRV!CsrImpersonateClient` at `0x180002e0f`
- `CSRSRV!CsrImpersonateClient` at `0x180002e99`
- `CSRSRV!CsrImpersonateClient` at `0x180003057`

## string_xrefs

- `0x180002f36`: `.Manifest`
- `0x18000302e`: `.Manifest`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCheckManifestAndDotLocal(
        unsigned __int16 *a1,
        USHORT *a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        int a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  __int64 v11; // rbx
  WCHAR *v12; // r15
  const WCHAR *v13; // rdx
  NTSTATUS ResourceStream; // ebx
  int v15; // edi
  BOOL v16; // eax
  const void **v17; // rbx
  unsigned __int16 v18; // cx
  int v19; // r8d
  int v20; // r9d
  WCHAR *v21; // r12
  PCWSTR *v22; // r13
  __int64 v23; // rdx
  WCHAR *Heap; // rax
  unsigned __int16 v25; // cx
  WCHAR *v27; // rax
  __int64 v28; // rcx
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v30; // [rsp+44h] [rbp-BCh]
  PVOID P; // [rsp+48h] [rbp-B8h]
  _QWORD *v32; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING v34; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-88h] BYREF
  USHORT *v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  _QWORD v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v40[2]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v41[6]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v44; // [rsp+238h] [rbp+138h]
  int v45; // [rsp+240h] [rbp+140h]
  __int64 v46; // [rsp+250h] [rbp+150h] BYREF
  unsigned int v47; // [rsp+258h] [rbp+158h]

  v38 = a7;
  v37 = a3;
  v40[0] = &v34;
  v33 = a1;
  v40[1] = &Destination;
  v36 = a2;
  v32 = a5;
  v11 = *a5;
  v12 = 0;
  v30 = a4 != 0;
  v29 = 0;
  P = 0;
  v39[1] = a2;
  v46 = 0;
  v47 = 0;
  v34 = 0;
  v39[0] = a1;
  Destination = 0;
  memset_0(v41, 0, 0x188u);
  v13 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v41[0] = 32;
  if ( v11 == -1 )
    v11 = 0;
  v42 = v11;
  if ( RtlInitUnicodeStringEx(&DestinationString, v13) < 0
    || (v45 = 12, v44 = &v46, (int)((__int64 (__fastcall *)(_QWORD, _DWORD *))g_CompatCacheServiceApi)(0, v41) < 0) )
  {
    v15 = 0;
  }
  else
  {
    v29 = v47 & 1;
    if ( ((v47 >> 1) & 1) != 0 )
    {
      *a9 |= 0x2000u;
      ResourceStream = 0;
      v15 = 1;
      if ( !a4 )
      {
        v16 = v30;
        goto LABEL_8;
      }
    }
    else
    {
      if ( !a4 )
      {
        ResourceStream = 0;
        if ( a6 && (v47 & 1) != 0 )
          *a9 |= 0x1000u;
        return (unsigned int)ResourceStream;
      }
      v15 = 1;
    }
  }
  if ( !(unsigned __int8)CsrImpersonateClient(0) )
    return (unsigned int)-1073741659;
  ResourceStream = BasepSxsCreateResourceStream((unsigned int)v39, (_DWORD)v32, v19, v20, v37, a4, a8);
  CsrRevertToSelf();
  if ( ResourceStream >= 0 )
  {
    *a9 |= 0x2000u;
    *(_BYTE *)(a8 + 2) = 4;
    goto LABEL_21;
  }
  if ( (unsigned int)(ResourceStream + 1073741687) <= 2 || ResourceStream == -1073741308 )
  {
    v16 = v30;
    if ( !v15 )
    {
LABEL_8:
      if ( !v16 )
      {
        v17 = (const void **)v36;
        v18 = *v36;
        if ( *v36 > 0xFFEBu )
          return (unsigned int)-1073741562;
        Destination.Length = *v36;
        if ( (unsigned __int16)(v18 + 20) < v18 )
          return (unsigned int)-1073741675;
        Destination.MaximumLength = v18 + 20;
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v18 + 20));
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        memcpy_0(Heap, v17[1], *(unsigned __int16 *)v17);
        Destination.Buffer = v12;
        ResourceStream = RtlAppendUnicodeToString(&Destination, L".Manifest");
        if ( ResourceStream < 0 )
          goto LABEL_38;
        v25 = *v33;
        if ( *v33 > 0xFFEBu )
        {
          ResourceStream = -1073741562;
LABEL_38:
          v21 = (WCHAR *)P;
          goto LABEL_39;
        }
        v34.Length = *v33;
        if ( (unsigned __int16)(v25 + 20) < v25 )
        {
          ResourceStream = -1073741675;
          v34.MaximumLength = -1;
          goto LABEL_38;
        }
        v34.MaximumLength = v25 + 20;
        v27 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v25 + 20));
        v21 = v27;
        if ( !v27 )
        {
          ResourceStream = -1073741801;
          goto LABEL_39;
        }
        memcpy_0(v27, *((const void **)v33 + 1), *v33);
        v34.Buffer = v21;
        ResourceStream = RtlAppendUnicodeToString(&v34, L".Manifest");
        if ( ResourceStream < 0 )
          goto LABEL_39;
        if ( !(unsigned __int8)CsrImpersonateClient(0) )
        {
          ResourceStream = -1073741659;
          goto LABEL_39;
        }
        ResourceStream = BasepSxsCreateFileStreamEx(v28, v40, 0, v38, a8);
        CsrRevertToSelf();
        if ( ResourceStream < 0 )
        {
          if ( !(unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)ResourceStream) )
            goto LABEL_39;
          if ( v15 )
          {
            *a9 &= ~0x2000u;
            v22 = (PCWSTR *)v33;
            CompatCacheDeleteFusionState(*((PCWSTR *)v33 + 1));
            goto LABEL_24;
          }
LABEL_23:
          v22 = (PCWSTR *)v33;
LABEL_24:
          if ( (*a9 & 0x2000) == 0 && a6 )
          {
            if ( !(unsigned __int8)CsrImpersonateClient(0) )
            {
              ResourceStream = -1073741659;
              goto LABEL_60;
            }
            ResourceStream = BasepCheckDotLocalExists(v36, v23, &v29);
            CsrRevertToSelf();
            if ( ResourceStream < 0 )
            {
LABEL_60:
              if ( !v12 )
              {
LABEL_40:
                if ( v21 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
                return (unsigned int)ResourceStream;
              }
LABEL_39:
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
              goto LABEL_40;
            }
            if ( v29 )
              *a9 |= 0x1000u;
          }
          CompatCacheSetFusionState(v22[1]);
          ResourceStream = 0;
          goto LABEL_60;
        }
        *(_BYTE *)(a8 + 2) = 5;
        *a9 |= 0x2000u;
        v21 = 0;
LABEL_22:
        if ( v15 )
          goto LABEL_60;
        goto LABEL_23;
      }
LABEL_21:
      v21 = 0;
      goto LABEL_22;
    }
  }
  return (unsigned int)ResourceStream;
}

```

## disassembly

```asm
0x180002c50  push    rbp
0x180002c52  push    rbx
0x180002c53  push    rsi
0x180002c54  push    rdi
0x180002c55  push    r12
0x180002c57  push    r13
0x180002c59  push    r14
0x180002c5b  push    r15
0x180002c5d  lea     rbp, [rsp-178h]
0x180002c65  sub     rsp, 278h
0x180002c6c  mov     rax, cs:__security_cookie
0x180002c73  xor     rax, rsp
0x180002c76  mov     [rbp+1B0h+var_50], rax
0x180002c7d  mov     rax, [rbp+1B0h+arg_30]
0x180002c84  mov     rdi, rcx
0x180002c87  mov     r13, [rbp+1B0h+arg_38]
0x180002c8e  xorps   xmm0, xmm0
0x180002c91  mov     r14, [rbp+1B0h+arg_40]
0x180002c98  xorps   xmm1, xmm1
0x180002c9b  mov     [rbp+1B0h+var_218], rax
0x180002c9f  mov     r12d, r9d
0x180002ca2  mov     [rbp+1B0h+var_220], r8
0x180002ca6  lea     rax, [rsp+2B0h+var_248]
0x180002cab  xor     r8d, r8d
0x180002cae  mov     [rbp+1B0h+var_200], rax
0x180002cb2  lea     rax, [rsp+2B0h+Destination]
0x180002cb7  mov     [rsp+2B0h+var_250], rcx
0x180002cbc  mov     rcx, [rbp+1B0h+arg_20]
0x180002cc3  test    r9d, r9d
0x180002cc6  mov     [rbp+1B0h+var_1F8], rax
0x180002cca  mov     esi, r8d
0x180002ccd  mov     eax, r8d
0x180002cd0  mov     [rbp+1B0h+var_228], rdx
0x180002cd4  setnz   al
0x180002cd7  mov     [rsp+2B0h+var_258], rcx
0x180002cdc  mov     rbx, [rcx]
0x180002cdf  mov     r15d, r8d
0x180002ce2  mov     [rsp+2B0h+var_26C], eax
0x180002ce6  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x180002cea  xor     eax, eax
0x180002cec  mov     [rsp+2B0h+var_270], r8d
0x180002cf1  mov     [rsp+2B0h+P], r8
0x180002cf6  mov     r8d, 188h; Size
0x180002cfc  mov     [rbp+1B0h+var_208], rdx
0x180002d00  xor     edx, edx; Val
0x180002d02  mov     [rbp+1B0h+var_60], rax
0x180002d09  mov     [rbp+1B0h+var_58], eax
0x180002d0f  movups  xmmword ptr [rsp+2B0h+var_248.Length], xmm0
0x180002d14  mov     [rbp+1B0h+var_210], rdi
0x180002d18  movups  xmmword ptr [rsp+2B0h+Destination.Length], xmm1
0x180002d1d  call    memset_0
0x180002d22  mov     rdx, [rdi+8]; SourceString
0x180002d26  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x180002d2a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002d2e  mov     [rbp+1B0h+var_1F0], 20h ; ' '
0x180002d35  cmovz   rbx, rsi
0x180002d39  mov     [rbp+1B0h+var_1D8], rbx
0x180002d3d  call    cs:__imp_RtlInitUnicodeStringEx
0x180002d44  nop     dword ptr [rax+rax+00h]
0x180002d49  test    eax, eax
0x180002d4b  js      loc_180002E09
0x180002d51  lea     rax, [rbp+1B0h+var_60]
0x180002d58  mov     [rbp+1B0h+var_70], 0Ch
0x180002d62  mov     [rbp+1B0h+var_78], rax
0x180002d69  lea     rdx, [rbp+1B0h+var_1F0]
0x180002d6d  mov     rax, cs:g_CompatCacheServiceApi
0x180002d74  xor     ecx, ecx
0x180002d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7b  test    eax, eax
0x180002d7d  js      loc_180002E09
0x180002d83  mov     esi, [rbp+1B0h+var_58]
0x180002d89  mov     eax, esi
0x180002d8b  and     eax, 1
0x180002d8e  shr     esi, 1
0x180002d90  mov     [rsp+2B0h+var_270], eax
0x180002d94  and     esi, 1
0x180002d97  jz      short loc_180002DD9
0x180002d99  or      dword ptr [r14], 2000h
0x180002da0  xor     eax, eax
0x180002da2  mov     ebx, eax
0x180002da4  lea     edi, [rax+1]
0x180002da7  test    r12d, r12d
0x180002daa  jnz     short loc_180002E0D
0x180002dac  mov     eax, [rsp+2B0h+var_26C]
0x180002db0  test    eax, eax
0x180002db2  jnz     loc_180002E68
0x180002db8  mov     rbx, [rbp+1B0h+var_228]
0x180002dbc  mov     r12d, 0FFEBh
0x180002dc2  movzx   ecx, word ptr [rbx]
0x180002dc5  cmp     cx, r12w
0x180002dc9  jbe     loc_180002EDF
0x180002dcf  mov     ebx, 0C0000106h
0x180002dd4  jmp     loc_180002FB1
0x180002dd9  test    r12d, r12d
0x180002ddc  jnz     short loc_180002E02
0x180002dde  xor     ecx, ecx
0x180002de0  mov     ebx, ecx
0x180002de2  cmp     [rbp+1B0h+arg_28], ecx
0x180002de8  jz      loc_180002FB1
0x180002dee  test    eax, eax
0x180002df0  jz      loc_180002FB1
0x180002df6  or      dword ptr [r14], 1000h
0x180002dfd  jmp     loc_180002FB1
0x180002e02  mov     edi, 1
0x180002e07  jmp     short loc_180002E0D
0x180002e09  xor     eax, eax
0x180002e0b  mov     edi, eax
0x180002e0d  xor     ecx, ecx
0x180002e0f  call    cs:__imp_CsrImpersonateClient
0x180002e16  nop     dword ptr [rax+rax+00h]
0x180002e1b  test    al, al
0x180002e1d  jnz     short loc_180002E29
0x180002e1f  mov     ebx, 0C00000A5h
0x180002e24  jmp     loc_180002FB1
0x180002e29  mov     rax, [rbp+1B0h+var_220]
0x180002e2d  lea     rcx, [rbp+1B0h+var_210]
0x180002e31  mov     rdx, [rsp+2B0h+var_258]
0x180002e36  mov     [rsp+2B0h+var_280], r13
0x180002e3b  mov     [rsp+2B0h+var_288], r12d
0x180002e40  mov     [rsp+2B0h+var_290], rax
0x180002e45  call    BasepSxsCreateResourceStream
0x180002e4a  mov     ebx, eax
0x180002e4c  call    cs:__imp_CsrRevertToSelf
0x180002e53  nop     dword ptr [rax+rax+00h]
0x180002e58  test    ebx, ebx
0x180002e5a  js      short loc_180002EB7
0x180002e5c  or      dword ptr [r14], 2000h
0x180002e63  mov     byte ptr [r13+2], 4
0x180002e68  mov     r12, r15
0x180002e6b  test    edi, edi
0x180002e6d  jnz     loc_180003159
0x180002e73  mov     rdi, [rsp+2B0h+var_258]
0x180002e78  mov     r13, [rsp+2B0h+var_250]
0x180002e7d  test    dword ptr [r14], 2000h
0x180002e84  jnz     loc_18000313C
0x180002e8a  cmp     [rbp+1B0h+arg_28], 0
0x180002e91  jz      loc_18000313C
0x180002e97  xor     ecx, ecx
0x180002e99  call    cs:__imp_CsrImpersonateClient
0x180002ea0  nop     dword ptr [rax+rax+00h]
0x180002ea5  test    al, al
0x180002ea7  jnz     loc_18000310E
0x180002ead  mov     ebx, 0C00000A5h
0x180002eb2  jmp     loc_180003159
0x180002eb7  lea     eax, [rbx+3FFFFF77h]
0x180002ebd  cmp     eax, 2
0x180002ec0  jbe     short loc_180002ECE
0x180002ec2  cmp     ebx, 0C0000204h
0x180002ec8  jnz     loc_180002FB1
0x180002ece  mov     eax, [rsp+2B0h+var_26C]
0x180002ed2  test    edi, edi
0x180002ed4  jnz     loc_180002FB1
0x180002eda  jmp     loc_180002DB0
0x180002edf  lea     eax, [rcx+14h]
0x180002ee2  mov     [rsp+2B0h+Destination.Length], cx
0x180002ee7  cmp     ax, cx
0x180002eea  jb      loc_180003104
0x180002ef0  mov     [rsp+2B0h+Destination.MaximumLength], ax
0x180002ef5  xor     edx, edx; Flags
0x180002ef7  mov     rcx, gs:60h
0x180002f00  movzx   r8d, ax; Size
0x180002f04  mov     rcx, [rcx+30h]; HeapHandle
0x180002f08  call    cs:__imp_RtlAllocateHeap
0x180002f0f  nop     dword ptr [rax+rax+00h]
0x180002f14  mov     r15, rax
0x180002f17  test    rax, rax
0x180002f1a  jnz     short loc_180002F26
0x180002f1c  mov     ebx, 0C0000017h
0x180002f21  jmp     loc_180002FB1
0x180002f26  movzx   r8d, word ptr [rbx]; Size
0x180002f2a  mov     rcx, r15; void *
0x180002f2d  mov     rdx, [rbx+8]; Src
0x180002f31  call    memcpy_0
0x180002f36  lea     rdx, aManifest; ".Manifest"
0x180002f3d  mov     [rbp+1B0h+Destination.Buffer], r15
0x180002f41  lea     rcx, [rsp+2B0h+Destination]; Destination
0x180002f46  call    cs:__imp_RtlAppendUnicodeToString
0x180002f4d  nop     dword ptr [rax+rax+00h]
0x180002f52  mov     ebx, eax
0x180002f54  test    eax, eax
0x180002f56  js      short loc_180002F6B
0x180002f58  mov     rbx, [rsp+2B0h+var_250]
0x180002f5d  movzx   ecx, word ptr [rbx]
0x180002f60  cmp     cx, r12w
0x180002f64  jbe     short loc_180002FD7
0x180002f66  mov     ebx, 0C0000106h
0x180002f6b  mov     r12, [rsp+2B0h+P]
0x180002f70  mov     rcx, gs:60h
0x180002f79  mov     r8, r15; P
0x180002f7c  xor     edx, edx; Flags
0x180002f7e  mov     rcx, [rcx+30h]; HeapHandle
0x180002f82  call    cs:__imp_RtlFreeHeap
0x180002f89  nop     dword ptr [rax+rax+00h]
0x180002f8e  test    r12, r12
0x180002f91  jz      short loc_180002FB1
0x180002f93  mov     rcx, gs:60h
0x180002f9c  mov     r8, r12; P
0x180002f9f  xor     edx, edx; Flags
0x180002fa1  mov     rcx, [rcx+30h]; HeapHandle
0x180002fa5  call    cs:__imp_RtlFreeHeap
0x180002fac  nop     dword ptr [rax+rax+00h]
0x180002fb1  mov     eax, ebx
0x180002fb3  mov     rcx, [rbp+1B0h+var_50]
0x180002fba  xor     rcx, rsp; StackCookie
0x180002fbd  call    __security_check_cookie
0x180002fc2  add     rsp, 278h
0x180002fc9  pop     r15
0x180002fcb  pop     r14
0x180002fcd  pop     r13
0x180002fcf  pop     r12
0x180002fd1  pop     rdi
0x180002fd2  pop     rsi
0x180002fd3  pop     rbx
0x180002fd4  pop     rbp
0x180002fd5  retn
0x180002fd7  lea     eax, [rcx+14h]
0x180002fda  mov     [rsp+2B0h+var_248.Length], cx
0x180002fdf  cmp     ax, cx
0x180002fe2  jb      loc_1800030F0
0x180002fe8  mov     [rsp+2B0h+var_248.MaximumLength], ax
0x180002fed  xor     edx, edx; Flags
0x180002fef  mov     rcx, gs:60h
0x180002ff8  movzx   r8d, ax; Size
0x180002ffc  mov     rcx, [rcx+30h]; HeapHandle
0x180003000  call    cs:__imp_RtlAllocateHeap
0x180003007  nop     dword ptr [rax+rax+00h]
0x18000300c  mov     r12, rax
0x18000300f  test    rax, rax
0x180003012  jnz     short loc_18000301E
0x180003014  mov     ebx, 0C0000017h
0x180003019  jmp     loc_180002F70
0x18000301e  movzx   r8d, word ptr [rbx]; Size
0x180003022  mov     rcx, r12; void *
0x180003025  mov     rdx, [rbx+8]; Src
0x180003029  call    memcpy_0
0x18000302e  lea     rdx, aManifest; ".Manifest"
0x180003035  mov     [rsp+2B0h+var_248.Buffer], r12
0x18000303a  lea     rcx, [rsp+2B0h+var_248]; Destination
0x18000303f  call    cs:__imp_RtlAppendUnicodeToString
0x180003046  nop     dword ptr [rax+rax+00h]
0x18000304b  mov     ebx, eax
0x18000304d  test    eax, eax
0x18000304f  js      loc_180002F70
0x180003055  xor     ecx, ecx
0x180003057  call    cs:__imp_CsrImpersonateClient
0x18000305e  nop     dword ptr [rax+rax+00h]
0x180003063  test    al, al
0x180003065  jnz     short loc_180003071
0x180003067  mov     ebx, 0C00000A5h
0x18000306c  jmp     loc_180002F70
0x180003071  mov     r9, [rbp+1B0h+var_218]
0x180003075  lea     rdx, [rbp+1B0h+var_200]
0x180003079  xor     r8d, r8d
0x18000307c  mov     [rsp+2B0h+var_290], r13
0x180003081  call    BasepSxsCreateFileStreamEx
0x180003086  mov     ebx, eax
0x180003088  call    cs:__imp_CsrRevertToSelf
0x18000308f  nop     dword ptr [rax+rax+00h]
0x180003094  test    ebx, ebx
0x180003096  js      short loc_1800030B3
0x180003098  xor     eax, eax
0x18000309a  mov     byte ptr [r13+2], 5
0x18000309f  or      dword ptr [r14], 2000h
0x1800030a6  mov     r12d, eax
0x1800030a9  mov     esi, 1
0x1800030ae  jmp     loc_180002E6B
0x1800030b3  mov     ecx, ebx
0x1800030b5  call    BasepSxsIsStatusFileNotFoundEtc
0x1800030ba  test    eax, eax
0x1800030bc  jz      loc_180002F70
0x1800030c2  test    edi, edi
0x1800030c4  jz      loc_180002E73
0x1800030ca  and     dword ptr [r14], 0FFFFDFFFh
0x1800030d1  xor     eax, eax
0x1800030d3  mov     rdi, [rsp+2B0h+var_258]
0x1800030d8  mov     esi, eax
0x1800030da  mov     r13, [rsp+2B0h+var_250]
0x1800030df  mov     rdx, [rdi]
0x1800030e2  mov     rcx, [r13+8]; SourceString
0x1800030e6  call    CompatCacheDeleteFusionState
0x1800030eb  jmp     loc_180002E7D
0x1800030f0  mov     eax, 0FFFFh
0x1800030f5  mov     ebx, 0C0000095h
0x1800030fa  mov     [rsp+2B0h+var_248.MaximumLength], ax
0x1800030ff  jmp     loc_180002F6B
0x180003104  mov     ebx, 0C0000095h
0x180003109  jmp     loc_180002FB1
0x18000310e  mov     rcx, [rbp+1B0h+var_228]
0x180003112  lea     r8, [rsp+2B0h+var_270]
0x180003117  call    BasepCheckDotLocalExists
0x18000311c  mov     ebx, eax
0x18000311e  call    cs:__imp_CsrRevertToSelf
0x180003125  nop     dword ptr [rax+rax+00h]
0x18000312a  test    ebx, ebx
0x18000312c  js      short loc_180003159
0x18000312e  cmp     [rsp+2B0h+var_270], 0
0x180003133  jz      short loc_18000313C
0x180003135  or      dword ptr [r14], 1000h
0x18000313c  mov     r8d, [r14]
0x18000313f  mov     r9d, esi
  ... truncated ...
```
