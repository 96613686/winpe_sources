# BaseSrvSxsCheckManifestAndDotLocal

- ea: `0x180002d40`
- end: `0x18000322a`
- name: `BaseSrvSxsCheckManifestAndDotLocal`
- size: `1258`
- prototype: `__int64 __fastcall(unsigned __int16 *, USHORT *, __int64, int, __int64 *, int, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800028d0`

## callees

- `0x180002d40`
- `0x180003230`
- `0x180004020`
- `0x1800042b0`
- `0x180004310`
- `0x180006180`
- `0x180006b08`
- `0x180006cc1`
- `0x180006ccd`
- `0x180006cf0`
- `0x180008010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000300c`
- `ntdll!RtlFreeHeap` at `0x18000302f`
- `ntdll!RtlFreeHeap` at `0x18000300c`
- `ntdll!RtlFreeHeap` at `0x18000302f`
- `ntdll!RtlAllocateHeap` at `0x180002f92`
- `ntdll!RtlAllocateHeap` at `0x18000308a`
- `ntdll!RtlAllocateHeap` at `0x180002f92`
- `ntdll!RtlAllocateHeap` at `0x18000308a`
- `ntdll!RtlAppendUnicodeToString` at `0x180002fd0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800030c9`
- `ntdll!RtlAppendUnicodeToString` at `0x180002fd0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800030c9`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002e20`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002e20`
- `CSRSRV!CsrRevertToSelf` at `0x180002efb`
- `CSRSRV!CsrRevertToSelf` at `0x180003117`
- `CSRSRV!CsrRevertToSelf` at `0x1800031d9`
- `CSRSRV!CsrRevertToSelf` at `0x180002efb`
- `CSRSRV!CsrRevertToSelf` at `0x180003117`
- `CSRSRV!CsrRevertToSelf` at `0x1800031d9`
- `CSRSRV!CsrImpersonateClient` at `0x180002ebb`
- `CSRSRV!CsrImpersonateClient` at `0x1800030e1`
- `CSRSRV!CsrImpersonateClient` at `0x1800031b1`
- `CSRSRV!CsrImpersonateClient` at `0x180002ebb`
- `CSRSRV!CsrImpersonateClient` at `0x1800030e1`
- `CSRSRV!CsrImpersonateClient` at `0x1800031b1`

## string_xrefs

- `0x180002fc0`: `.Manifest`
- `0x1800030b8`: `.Manifest`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCheckManifestAndDotLocal(
        unsigned __int16 *a1,
        USHORT *a2,
        __int64 a3,
        int a4,
        __int64 *a5,
        int a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  WCHAR *v9; // r12
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  int v14; // esi
  NTSTATUS appended; // ebx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  WCHAR *v19; // r15
  const void **v20; // rbx
  unsigned __int16 v21; // cx
  WCHAR *Heap; // rax
  unsigned __int16 v23; // cx
  WCHAR *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  PVOID P; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING v32; // [rsp+60h] [rbp-A0h] BYREF
  USHORT *v33; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  _QWORD v37[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v38[3]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v39[6]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v42; // [rsp+238h] [rbp+138h]
  int v43; // [rsp+240h] [rbp+140h]
  __int64 v44; // [rsp+250h] [rbp+150h] BYREF
  unsigned int v45; // [rsp+258h] [rbp+158h]

  v9 = 0;
  v36 = a7;
  v30 = a8;
  v35 = a3;
  v38[0] = &v32;
  v33 = a2;
  v38[1] = &Destination;
  v31 = a1;
  v37[0] = a1;
  v37[1] = a2;
  v44 = 0;
  v45 = 0;
  v28 = 0;
  v32 = 0;
  P = 0;
  Destination = 0;
  memset_0(v39, 0, 0x188u);
  v12 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v13 = 0;
  if ( *a5 != -1 )
    v13 = *a5;
  v40 = v13;
  v39[0] = 32;
  if ( RtlInitUnicodeStringEx(&DestinationString, v12) < 0
    || (v43 = 12, v42 = &v44, (int)((__int64 (__fastcall *)(_QWORD, _DWORD *))g_CompatCacheServiceApi)(0, v39) < 0) )
  {
    v14 = 0;
  }
  else
  {
    v14 = 1;
    v28 = v45 & 1;
    if ( ((v45 >> 1) & 1) != 0 )
    {
      *a9 |= 0x2000u;
      if ( !a4 )
      {
LABEL_21:
        v20 = (const void **)v33;
        v21 = *v33;
        if ( *v33 > 0xFFEBu )
          return (unsigned int)-1073741562;
        Destination.Length = *v33;
        if ( (unsigned __int16)(v21 + 20) < v21 )
          return (unsigned int)-1073741675;
        Destination.MaximumLength = v21 + 20;
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v21 + 20));
        v9 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        memcpy_0(Heap, v20[1], *(unsigned __int16 *)v20);
        Destination.Buffer = v9;
        appended = RtlAppendUnicodeToString(&Destination, L".Manifest");
        if ( appended < 0 )
          goto LABEL_29;
        v23 = *v31;
        if ( *v31 > 0xFFEBu )
        {
          appended = -1073741562;
LABEL_29:
          v19 = (WCHAR *)P;
          goto LABEL_30;
        }
        v32.Length = *v31;
        if ( (unsigned __int16)(v23 + 20) < v23 )
        {
          appended = -1073741675;
          v32.MaximumLength = -1;
          goto LABEL_29;
        }
        v32.MaximumLength = v23 + 20;
        v25 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v23 + 20));
        v19 = v25;
        if ( !v25 )
        {
          appended = -1073741801;
          goto LABEL_30;
        }
        memcpy_0(v25, *((const void **)v31 + 1), *v31);
        v32.Buffer = v19;
        appended = RtlAppendUnicodeToString(&v32, L".Manifest");
        if ( appended < 0 )
          goto LABEL_30;
        if ( !(unsigned __int8)CsrImpersonateClient(0) )
        {
          appended = -1073741659;
          goto LABEL_30;
        }
        appended = BasepSxsCreateFileStreamEx(v26, v38, 0, v36, v30);
        CsrRevertToSelf();
        if ( appended < 0 )
        {
          if ( !(unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)appended) )
            goto LABEL_30;
          if ( v14 )
          {
            *a9 &= ~0x2000u;
            CompatCacheDeleteFusionState(*((PCWSTR *)v31 + 1));
          }
          goto LABEL_50;
        }
        v19 = 0;
        *(_BYTE *)(v30 + 2) = 5;
        *a9 |= 0x2000u;
LABEL_42:
        if ( v14 )
          goto LABEL_58;
LABEL_50:
        if ( (*a9 & 0x2000) == 0 && a6 )
        {
          if ( !(unsigned __int8)CsrImpersonateClient(0) )
          {
            appended = -1073741659;
            goto LABEL_58;
          }
          appended = BasepCheckDotLocalExists(v33, v27, &v28);
          CsrRevertToSelf();
          if ( appended < 0 )
          {
LABEL_58:
            if ( !v9 )
            {
LABEL_31:
              if ( v19 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
              return (unsigned int)appended;
            }
LABEL_30:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            goto LABEL_31;
          }
          if ( v28 )
            *a9 |= 0x1000u;
        }
        CompatCacheSetFusionState(*((PCWSTR *)v31 + 1));
        appended = 0;
        goto LABEL_58;
      }
    }
    else if ( !a4 )
    {
      appended = 0;
      if ( a6 && (v45 & 1) != 0 )
        *a9 |= 0x1000u;
      return (unsigned int)appended;
    }
  }
  if ( !(unsigned __int8)CsrImpersonateClient(0) )
    return (unsigned int)-1073741659;
  appended = BasepSxsCreateResourceStream((unsigned int)v37, (_DWORD)a5, v16, v17, v35, a4, v30);
  CsrRevertToSelf();
  if ( appended >= 0 )
  {
    v18 = v30;
    v19 = 0;
    *a9 |= 0x2000u;
    *(_BYTE *)(v18 + 2) = 4;
    goto LABEL_42;
  }
  if ( ((unsigned int)(appended + 1073741687) <= 2 || appended == -1073741308) && !v14 )
  {
    if ( a4 )
    {
      v19 = 0;
      goto LABEL_50;
    }
    goto LABEL_21;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180002d40  push    rbp
0x180002d42  push    rbx
0x180002d43  push    rsi
0x180002d44  push    rdi
0x180002d45  push    r12
0x180002d47  push    r13
0x180002d49  push    r14
0x180002d4b  push    r15
0x180002d4d  lea     rbp, [rsp-178h]
0x180002d55  sub     rsp, 278h
0x180002d5c  mov     rax, cs:__security_cookie
0x180002d63  xor     rax, rsp
0x180002d66  mov     [rbp+1B0h+var_50], rax
0x180002d6d  mov     rax, [rbp+1B0h+arg_30]
0x180002d74  xor     r12d, r12d
0x180002d77  mov     r13, [rbp+1B0h+arg_20]
0x180002d7e  mov     rsi, rcx
0x180002d81  mov     r14, [rbp+1B0h+arg_40]
0x180002d88  xorps   xmm0, xmm0
0x180002d8b  mov     [rbp+1B0h+var_220], rax
0x180002d8f  xorps   xmm1, xmm1
0x180002d92  mov     rax, [rbp+1B0h+arg_38]
0x180002d99  mov     r15d, r9d
0x180002d9c  mov     [rsp+2B0h+var_260], rax
0x180002da1  mov     edi, r12d
0x180002da4  lea     rax, [rsp+2B0h+var_250]
0x180002da9  mov     [rbp+1B0h+var_228], r8
0x180002dad  mov     [rbp+1B0h+var_208], rax
0x180002db1  mov     r8d, 188h; Size
0x180002db7  lea     rax, [rsp+2B0h+Destination]
0x180002dbc  mov     [rsp+2B0h+var_240], rdx
0x180002dc1  mov     [rbp+1B0h+var_200], rax
0x180002dc5  xor     eax, eax
0x180002dc7  mov     [rsp+2B0h+var_258], rcx
0x180002dcc  mov     [rbp+1B0h+var_218], rcx
0x180002dd0  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x180002dd4  mov     [rbp+1B0h+var_210], rdx
0x180002dd8  xor     edx, edx; Val
0x180002dda  mov     [rbp+1B0h+var_60], rax
0x180002de1  mov     [rbp+1B0h+var_58], eax
0x180002de7  mov     [rsp+2B0h+var_270], r12d
0x180002dec  movups  xmmword ptr [rsp+2B0h+var_250.Length], xmm0
0x180002df1  mov     [rsp+2B0h+P], r12
0x180002df6  movups  xmmword ptr [rsp+2B0h+Destination.Length], xmm1
0x180002dfb  call    memset_0
0x180002e00  cmp     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x180002e05  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x180002e09  mov     rdx, [rsi+8]; SourceString
0x180002e0d  mov     eax, r12d
0x180002e10  cmovnz  rax, [r13+0]
0x180002e15  mov     [rbp+1B0h+var_1D8], rax
0x180002e19  mov     [rbp+1B0h+var_1F0], 20h ; ' '
0x180002e20  call    cs:__imp_RtlInitUnicodeStringEx
0x180002e27  nop     dword ptr [rax+rax+00h]
0x180002e2c  test    eax, eax
0x180002e2e  js      loc_180002EB6
0x180002e34  lea     rax, [rbp+1B0h+var_60]
0x180002e3b  mov     [rbp+1B0h+var_70], 0Ch
0x180002e45  mov     [rbp+1B0h+var_78], rax
0x180002e4c  lea     rdx, [rbp+1B0h+var_1F0]
0x180002e50  mov     rax, cs:g_CompatCacheServiceApi
0x180002e57  xor     ecx, ecx
0x180002e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5e  test    eax, eax
0x180002e60  js      short loc_180002EB6
0x180002e62  mov     edi, [rbp+1B0h+var_58]
0x180002e68  mov     esi, 1
0x180002e6d  mov     eax, edi
0x180002e6f  shr     edi, 1
0x180002e71  and     eax, 1
0x180002e74  mov     [rsp+2B0h+var_270], eax
0x180002e78  and     edi, 1
0x180002e7b  jz      short loc_180002E8E
0x180002e7d  or      dword ptr [r14], 2000h
0x180002e84  test    r15d, r15d
0x180002e87  jnz     short loc_180002EB9
0x180002e89  jmp     loc_180002F4B
0x180002e8e  test    r15d, r15d
0x180002e91  jnz     short loc_180002EB9
0x180002e93  mov     ebx, r12d
0x180002e96  cmp     [rbp+1B0h+arg_28], ebx
0x180002e9c  jz      loc_18000303B
0x180002ea2  test    eax, eax
0x180002ea4  jz      loc_18000303B
0x180002eaa  or      dword ptr [r14], 1000h
0x180002eb1  jmp     loc_18000303B
0x180002eb6  mov     esi, r12d
0x180002eb9  xor     ecx, ecx
0x180002ebb  call    cs:__imp_CsrImpersonateClient
0x180002ec2  nop     dword ptr [rax+rax+00h]
0x180002ec7  test    al, al
0x180002ec9  jnz     short loc_180002ED5
0x180002ecb  mov     ebx, 0C00000A5h
0x180002ed0  jmp     loc_18000303B
0x180002ed5  mov     rax, [rsp+2B0h+var_260]
0x180002eda  lea     rcx, [rbp+1B0h+var_218]
0x180002ede  mov     [rsp+2B0h+var_280], rax
0x180002ee3  mov     rdx, r13
0x180002ee6  mov     rax, [rbp+1B0h+var_228]
0x180002eea  mov     [rsp+2B0h+var_288], r15d
0x180002eef  mov     [rsp+2B0h+var_290], rax
0x180002ef4  call    BasepSxsCreateResourceStream
0x180002ef9  mov     ebx, eax
0x180002efb  call    cs:__imp_CsrRevertToSelf
0x180002f02  nop     dword ptr [rax+rax+00h]
0x180002f07  test    ebx, ebx
0x180002f09  js      short loc_180002F23
0x180002f0b  mov     rax, [rsp+2B0h+var_260]
0x180002f10  mov     r15, r12
0x180002f13  or      dword ptr [r14], 2000h
0x180002f1a  mov     byte ptr [rax+2], 4
0x180002f1e  jmp     loc_18000313F
0x180002f23  lea     eax, [rbx+3FFFFF77h]
0x180002f29  cmp     eax, 2
0x180002f2c  jbe     short loc_180002F3A
0x180002f2e  cmp     ebx, 0C0000204h
0x180002f34  jnz     loc_18000303B
0x180002f3a  test    esi, esi
0x180002f3c  jnz     loc_18000303B
0x180002f42  test    r15d, r15d
0x180002f45  jnz     loc_18000319A
0x180002f4b  mov     rbx, [rsp+2B0h+var_240]
0x180002f50  mov     r15d, 0FFEBh
0x180002f56  movzx   ecx, word ptr [rbx]
0x180002f59  cmp     cx, r15w
0x180002f5d  jbe     short loc_180002F69
0x180002f5f  mov     ebx, 0C0000106h
0x180002f64  jmp     loc_18000303B
0x180002f69  lea     eax, [rcx+14h]
0x180002f6c  mov     [rsp+2B0h+Destination.Length], cx
0x180002f71  cmp     ax, cx
0x180002f74  jb      loc_180003190
0x180002f7a  mov     [rsp+2B0h+Destination.MaximumLength], ax
0x180002f7f  xor     edx, edx; Flags
0x180002f81  mov     rcx, gs:60h
0x180002f8a  movzx   r8d, ax; Size
0x180002f8e  mov     rcx, [rcx+30h]; HeapHandle
0x180002f92  call    cs:__imp_RtlAllocateHeap
0x180002f99  nop     dword ptr [rax+rax+00h]
0x180002f9e  mov     r12, rax
0x180002fa1  test    rax, rax
0x180002fa4  jnz     short loc_180002FB0
0x180002fa6  mov     ebx, 0C0000017h
0x180002fab  jmp     loc_18000303B
0x180002fb0  movzx   r8d, word ptr [rbx]; Size
0x180002fb4  mov     rcx, r12; void *
0x180002fb7  mov     rdx, [rbx+8]; Src
0x180002fbb  call    memcpy_0
0x180002fc0  lea     rdx, aManifest; ".Manifest"
0x180002fc7  mov     [rbp+1B0h+Destination.Buffer], r12
0x180002fcb  lea     rcx, [rsp+2B0h+Destination]; Destination
0x180002fd0  call    cs:__imp_RtlAppendUnicodeToString
0x180002fd7  nop     dword ptr [rax+rax+00h]
0x180002fdc  mov     ebx, eax
0x180002fde  test    eax, eax
0x180002fe0  js      short loc_180002FF5
0x180002fe2  mov     rbx, [rsp+2B0h+var_258]
0x180002fe7  movzx   ecx, word ptr [rbx]
0x180002fea  cmp     cx, r15w
0x180002fee  jbe     short loc_180003061
0x180002ff0  mov     ebx, 0C0000106h
0x180002ff5  mov     r15, [rsp+2B0h+P]
0x180002ffa  mov     rcx, gs:60h
0x180003003  mov     r8, r12; P
0x180003006  xor     edx, edx; Flags
0x180003008  mov     rcx, [rcx+30h]; HeapHandle
0x18000300c  call    cs:__imp_RtlFreeHeap
0x180003013  nop     dword ptr [rax+rax+00h]
0x180003018  test    r15, r15
0x18000301b  jz      short loc_18000303B
0x18000301d  mov     rcx, gs:60h
0x180003026  mov     r8, r15; P
0x180003029  xor     edx, edx; Flags
0x18000302b  mov     rcx, [rcx+30h]; HeapHandle
0x18000302f  call    cs:__imp_RtlFreeHeap
0x180003036  nop     dword ptr [rax+rax+00h]
0x18000303b  mov     eax, ebx
0x18000303d  mov     rcx, [rbp+1B0h+var_50]
0x180003044  xor     rcx, rsp; StackCookie
0x180003047  call    __security_check_cookie
0x18000304c  add     rsp, 278h
0x180003053  pop     r15
0x180003055  pop     r14
0x180003057  pop     r13
0x180003059  pop     r12
0x18000305b  pop     rdi
0x18000305c  pop     rsi
0x18000305d  pop     rbx
0x18000305e  pop     rbp
0x18000305f  retn
0x180003061  lea     eax, [rcx+14h]
0x180003064  mov     [rsp+2B0h+var_250.Length], cx
0x180003069  cmp     ax, cx
0x18000306c  jb      loc_18000317C
0x180003072  mov     [rsp+2B0h+var_250.MaximumLength], ax
0x180003077  xor     edx, edx; Flags
0x180003079  mov     rcx, gs:60h
0x180003082  movzx   r8d, ax; Size
0x180003086  mov     rcx, [rcx+30h]; HeapHandle
0x18000308a  call    cs:__imp_RtlAllocateHeap
0x180003091  nop     dword ptr [rax+rax+00h]
0x180003096  mov     r15, rax
0x180003099  test    rax, rax
0x18000309c  jnz     short loc_1800030A8
0x18000309e  mov     ebx, 0C0000017h
0x1800030a3  jmp     loc_180002FFA
0x1800030a8  movzx   r8d, word ptr [rbx]; Size
0x1800030ac  mov     rcx, r15; void *
0x1800030af  mov     rdx, [rbx+8]; Src
0x1800030b3  call    memcpy_0
0x1800030b8  lea     rdx, aManifest; ".Manifest"
0x1800030bf  mov     [rsp+2B0h+var_250.Buffer], r15
0x1800030c4  lea     rcx, [rsp+2B0h+var_250]; Destination
0x1800030c9  call    cs:__imp_RtlAppendUnicodeToString
0x1800030d0  nop     dword ptr [rax+rax+00h]
0x1800030d5  mov     ebx, eax
0x1800030d7  test    eax, eax
0x1800030d9  js      loc_180002FFA
0x1800030df  xor     ecx, ecx
0x1800030e1  call    cs:__imp_CsrImpersonateClient
0x1800030e8  nop     dword ptr [rax+rax+00h]
0x1800030ed  test    al, al
0x1800030ef  jnz     short loc_1800030FB
0x1800030f1  mov     ebx, 0C00000A5h
0x1800030f6  jmp     loc_180002FFA
0x1800030fb  mov     rax, [rsp+2B0h+var_260]
0x180003100  lea     rdx, [rbp+1B0h+var_208]
0x180003104  mov     r9, [rbp+1B0h+var_220]
0x180003108  xor     r8d, r8d
0x18000310b  mov     [rsp+2B0h+var_290], rax
0x180003110  call    BasepSxsCreateFileStreamEx
0x180003115  mov     ebx, eax
0x180003117  call    cs:__imp_CsrRevertToSelf
0x18000311e  nop     dword ptr [rax+rax+00h]
0x180003123  test    ebx, ebx
0x180003125  js      short loc_180003148
0x180003127  mov     rax, [rsp+2B0h+var_260]
0x18000312c  xor     r15d, r15d
0x18000312f  mov     edi, 1
0x180003134  mov     byte ptr [rax+2], 5
0x180003138  or      dword ptr [r14], 2000h
0x18000313f  test    esi, esi
0x180003141  jz      short loc_18000319D
0x180003143  jmp     loc_18000321C
0x180003148  mov     ecx, ebx
0x18000314a  call    BasepSxsIsStatusFileNotFoundEtc
0x18000314f  test    eax, eax
0x180003151  jz      loc_180002FFA
0x180003157  test    esi, esi
0x180003159  jz      short loc_18000319D
0x18000315b  and     dword ptr [r14], 0FFFFDFFFh
0x180003162  xor     edi, edi
0x180003164  mov     rcx, [rsp+2B0h+var_258]
0x180003169  mov     rdx, [r13+0]
0x18000316d  mov     rcx, [rcx+8]; SourceString
0x180003171  call    CompatCacheDeleteFusionState
0x180003176  xor     ebx, ebx
0x180003178  xor     esi, esi
0x18000317a  jmp     short loc_18000319D
0x18000317c  mov     eax, 0FFFFh
0x180003181  mov     ebx, 0C0000095h
0x180003186  mov     [rsp+2B0h+var_250.MaximumLength], ax
0x18000318b  jmp     loc_180002FF5
0x180003190  mov     ebx, 0C0000095h
0x180003195  jmp     loc_18000303B
0x18000319a  mov     r15, r12
0x18000319d  test    dword ptr [r14], 2000h
0x1800031a4  jnz     short loc_1800031F7
0x1800031a6  cmp     [rbp+1B0h+arg_28], 0
0x1800031ad  jz      short loc_1800031F7
0x1800031af  xor     ecx, ecx
0x1800031b1  call    cs:__imp_CsrImpersonateClient
0x1800031b8  nop     dword ptr [rax+rax+00h]
0x1800031bd  test    al, al
0x1800031bf  jnz     short loc_1800031C8
0x1800031c1  mov     ebx, 0C00000A5h
0x1800031c6  jmp     short loc_18000321C
0x1800031c8  mov     rcx, [rsp+2B0h+var_240]
0x1800031cd  lea     r8, [rsp+2B0h+var_270]
0x1800031d2  call    BasepCheckDotLocalExists
0x1800031d7  mov     ebx, eax
0x1800031d9  call    cs:__imp_CsrRevertToSelf
0x1800031e0  nop     dword ptr [rax+rax+00h]
0x1800031e5  test    ebx, ebx
0x1800031e7  js      short loc_18000321C
0x1800031e9  cmp     [rsp+2B0h+var_270], 0
0x1800031ee  jz      short loc_1800031F7
0x1800031f0  or      dword ptr [r14], 1000h
0x1800031f7  test    esi, esi
0x1800031f9  jnz     short loc_18000321C
0x1800031fb  mov     rax, [rsp+2B0h+var_258]
0x180003200  mov     r9d, edi
0x180003203  mov     r8d, [r14]
0x180003206  mov     rdx, [r13+0]
0x18000320a  and     r8d, 1000h
0x180003211  mov     rcx, [rax+8]; SourceString
0x180003215  call    CompatCacheSetFusionState
0x18000321a  xor     ebx, ebx
0x18000321c  test    r12, r12
0x18000321f  jnz     loc_180002FFA
  ... truncated ...
```
