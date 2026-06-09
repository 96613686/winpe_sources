# EventJoinFieldElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x14003451c`
- end: `0x1400347bc`
- name: `?EventJoinFieldElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140032dcc`

## callees

- `0x140016808`
- `0x14003406c`
- `0x14003413c`
- `0x140034230`
- `0x140034318`
- `0x14003451c`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 result; // rax
  __int64 v7; // rcx
  struct _UNICODE_STRING v8; // xmm0
  WCHAR *v9; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v10; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING v12; // [rsp+40h] [rbp-20h]
  struct _UNICODE_STRING v13; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+20h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+98h] [rbp+38h] BYREF

  v2 = *((_QWORD *)a1 + 10);
  v9 = 0;
  v15 = 0;
  v14 = 0;
  v12 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  if ( *((_DWORD *)a1 + 12) != 6 )
  {
    v11 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
    if ( EqualString(&v11, L"EqualJoin", 0) )
      return 0;
  }
  v5 = v2 + 216;
  if ( (*(_BYTE *)(v5 + 176) & 8) != 0 )
  {
    v5 += 184;
    if ( (*(_BYTE *)(v5 + 176) & 8) != 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v14);
      PrintMessage(0x459u, v14);
      return 3221745201LL;
    }
  }
  for ( result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
        !(_DWORD)result;
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v9, &v15);
    v7 = *((_QWORD *)a1 + 3);
    v12.Buffer = v9;
    v10 = 0;
    v12.MaximumLength = 2 * v15;
    v12.Length = 2 * v15;
    v16 = 0;
    v11 = 0;
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v7 + 128LL))(v7, &v10, &v16);
    v8 = v12;
    v11.Buffer = v10;
    v13 = v12;
    v11.MaximumLength = 2 * v16;
    v11.Length = 2 * v16;
    if ( EqualString(&v13, L"field", 0) )
    {
      result = EventJoinFieldAttributeField(a1, &v11, (struct _TRACERPT_JOINFIELD *)v5);
    }
    else
    {
      v13 = v8;
      if ( EqualString(&v13, L"payloadGuid", 0) )
      {
        result = EventJoinFieldAttributeProviderID(a1, &v11, (struct _TRACERPT_JOINFIELD *)v5);
      }
      else
      {
        v13 = v8;
        if ( EqualString(&v13, L"payloadId", 0) )
        {
          result = EventJoinFieldAttributeEventID(a1, &v11, (struct _TRACERPT_JOINFIELD *)v5);
        }
        else
        {
          v13 = v8;
          if ( !EqualString(&v13, L"version", 0) )
            continue;
          result = EventJoinFieldAttributeVersion(a1, &v11, (struct _TRACERPT_JOINFIELD *)v5);
        }
      }
    }
    if ( (_DWORD)result )
      return result;
  }
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)(v5 + 176) & 0xB) == 0xB )
    {
      *((_QWORD *)a1 + 13) = v5;
      return 0;
    }
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v14);
    if ( (*(_BYTE *)(v5 + 176) & 8) == 0 )
      PrintMessage(0x45Au, v14);
    if ( (*(_BYTE *)(v5 + 176) & 1) == 0 )
      PrintMessage(0x405u, v14);
    if ( (*(_BYTE *)(v5 + 176) & 2) == 0 )
      PrintMessage(0x406u, v14);
    return 3221745169LL;
  }
  return result;
}

```

## disassembly

```asm
0x14003451c  mov     [rsp-18h+arg_8], rbx
0x140034521  push    rbp
0x140034522  push    rsi
0x140034523  push    rdi
0x140034524  mov     rbp, rsp
0x140034527  sub     rsp, 60h
0x14003452b  mov     rbx, [rcx+50h]
0x14003452f  xorps   xmm0, xmm0
0x140034532  mov     [rbp+var_40], 0
0x14003453a  mov     rdi, rcx
0x14003453d  mov     [rbp+arg_10], 0
0x140034544  mov     [rbp+arg_0], 0
0x14003454b  movups  [rbp+var_20], xmm0
0x14003454f  test    rbx, rbx
0x140034552  jz      loc_14003471E
0x140034558  test    rdx, rdx
0x14003455b  jz      loc_14003471E
0x140034561  cmp     dword ptr [rcx+30h], 6
0x140034565  mov     rsi, [rcx+18h]
0x140034569  jz      short loc_14003458F
0x14003456b  movups  xmm0, xmmword ptr [rdx+8]
0x14003456f  xor     r8d, r8d; unsigned __int8
0x140034572  lea     rdx, aEqualjoin; "EqualJoin"
0x140034579  lea     rcx, [rbp+var_30]; struct _UNICODE_STRING
0x14003457d  movdqu  xmmword ptr [rbp+var_30.Length], xmm0
0x140034582  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034587  test    al, al
0x140034589  jnz     loc_14003471E
0x14003458f  add     rbx, 0D8h
0x140034596  test    byte ptr [rbx+0B0h], 8
0x14003459d  jz      short loc_1400345B3
0x14003459f  add     rbx, 0B8h
0x1400345a6  test    byte ptr [rbx+0B0h], 8
0x1400345ad  jnz     loc_14003478F
0x1400345b3  mov     rax, [rsi]
0x1400345b6  mov     rax, [rax+40h]
0x1400345ba  jmp     loc_1400346FC
0x1400345bf  inc     dword ptr [rdi+2Ch]
0x1400345c2  lea     r8, [rbp+arg_10]
0x1400345c6  mov     rax, [rsi]
0x1400345c9  lea     rdx, [rbp+var_40]
0x1400345cd  mov     rcx, rsi
0x1400345d0  mov     rax, [rax+70h]
0x1400345d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400345d9  mov     rax, [rbp+var_40]
0x1400345dd  lea     r8, [rbp+arg_18]
0x1400345e1  mov     rcx, [rdi+18h]
0x1400345e5  lea     rdx, [rbp+var_38]
0x1400345e9  mov     qword ptr [rbp+var_20+8], rax
0x1400345ed  xorps   xmm0, xmm0
0x1400345f0  movzx   eax, word ptr [rbp+arg_10]
0x1400345f4  add     ax, ax
0x1400345f7  mov     [rbp+var_38], 0
0x1400345ff  mov     word ptr [rbp+var_20+2], ax
0x140034603  mov     word ptr [rbp+var_20], ax
0x140034607  mov     [rbp+arg_18], 0
0x14003460e  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140034612  mov     rax, [rcx]
0x140034615  mov     rax, [rax+80h]
0x14003461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034621  mov     rax, [rbp+var_38]
0x140034625  lea     rdx, aField; "field"
0x14003462c  movaps  xmm0, [rbp+var_20]
0x140034630  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034634  mov     [rbp+var_30.Buffer], rax
0x140034638  xor     r8d, r8d; unsigned __int8
0x14003463b  movzx   eax, word ptr [rbp+arg_18]
0x14003463f  add     ax, ax
0x140034642  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x140034647  mov     [rbp+var_30.MaximumLength], ax
0x14003464b  mov     [rbp+var_30.Length], ax
0x14003464f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034654  test    al, al
0x140034656  jz      short loc_14003466C
0x140034658  mov     r8, rbx; struct _TRACERPT_JOINFIELD *
0x14003465b  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x14003465f  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034662  call    ?EventJoinFieldAttributeField@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z; EventJoinFieldAttributeField(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)
0x140034667  jmp     loc_1400346F1
0x14003466c  xor     r8d, r8d; unsigned __int8
0x14003466f  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x140034674  lea     rdx, aPayloadguid; "payloadGuid"
0x14003467b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003467f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034684  test    al, al
0x140034686  jz      short loc_140034699
0x140034688  mov     r8, rbx; struct _TRACERPT_JOINFIELD *
0x14003468b  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x14003468f  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034692  call    ?EventJoinFieldAttributeProviderID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z; EventJoinFieldAttributeProviderID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)
0x140034697  jmp     short loc_1400346F1
0x140034699  xor     r8d, r8d; unsigned __int8
0x14003469c  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x1400346a1  lea     rdx, aPayloadid; "payloadId"
0x1400346a8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400346ac  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400346b1  test    al, al
0x1400346b3  jz      short loc_1400346C6
0x1400346b5  mov     r8, rbx; struct _TRACERPT_JOINFIELD *
0x1400346b8  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x1400346bc  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400346bf  call    ?EventJoinFieldAttributeEventID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z; EventJoinFieldAttributeEventID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)
0x1400346c4  jmp     short loc_1400346F1
0x1400346c6  xor     r8d, r8d; unsigned __int8
0x1400346c9  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x1400346ce  lea     rdx, aVersion; "version"
0x1400346d5  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400346d9  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400346de  test    al, al
0x1400346e0  jz      short loc_1400346F5
0x1400346e2  mov     r8, rbx; struct _TRACERPT_JOINFIELD *
0x1400346e5  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x1400346e9  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400346ec  call    ?EventJoinFieldAttributeVersion@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z; EventJoinFieldAttributeVersion(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)
0x1400346f1  test    eax, eax
0x1400346f3  jnz     short loc_140034720
0x1400346f5  mov     rax, [rsi]
0x1400346f8  mov     rax, [rax+48h]
0x1400346fc  mov     rcx, rsi
0x1400346ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034704  test    eax, eax
0x140034706  jz      loc_1400345BF
0x14003470c  js      short loc_140034720
0x14003470e  mov     al, [rbx+0B0h]
0x140034714  and     al, 0Bh
0x140034716  cmp     al, 0Bh
0x140034718  jnz     short loc_140034730
0x14003471a  mov     [rdi+68h], rbx
0x14003471e  xor     eax, eax
0x140034720  mov     rbx, [rsp+60h+arg_8]
0x140034728  add     rsp, 60h
0x14003472c  pop     rdi
0x14003472d  pop     rsi
0x14003472e  pop     rbp
0x14003472f  retn
0x140034730  mov     rax, [rsi]
0x140034733  lea     rdx, [rbp+arg_0]
0x140034737  mov     rcx, rsi
0x14003473a  mov     rax, [rax+0A8h]
0x140034741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034746  test    byte ptr [rbx+0B0h], 8
0x14003474d  jnz     short loc_14003475C
0x14003474f  mov     edx, [rbp+arg_0]
0x140034752  mov     ecx, 45Ah; unsigned int
0x140034757  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003475c  test    byte ptr [rbx+0B0h], 1
0x140034763  jnz     short loc_140034772
0x140034765  mov     edx, [rbp+arg_0]
0x140034768  mov     ecx, 405h; unsigned int
0x14003476d  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034772  test    byte ptr [rbx+0B0h], 2
0x140034779  jnz     short loc_140034788
0x14003477b  mov     edx, [rbp+arg_0]
0x14003477e  mov     ecx, 406h; unsigned int
0x140034783  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034788  mov     eax, 0C007EE11h
0x14003478d  jmp     short loc_140034720
0x14003478f  mov     rax, [rsi]
0x140034792  lea     rdx, [rbp+arg_0]
0x140034796  mov     rcx, rsi
0x140034799  mov     rax, [rax+0A8h]
0x1400347a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400347a5  mov     edx, [rbp+arg_0]
0x1400347a8  mov     ecx, 459h; unsigned int
0x1400347ad  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400347b2  mov     eax, 0C007EE31h
0x1400347b7  jmp     loc_140034720
```
