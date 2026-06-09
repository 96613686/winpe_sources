# SrvNetWskReceiveComplete

- ea: `0x1400027a0`
- end: `0x1400029fb`
- name: `SrvNetWskReceiveComplete`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002060`
- `0x1400027a0`
- `0x140002a10`
- `0x14000380c`
- `0x140017bd4`
- `0x1400189b4`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400027c6`
- `ntoskrnl!IoFreeIrp` at `0x1400027c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000290f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000290f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027fa`

## pseudocode

```c
__int64 __fastcall SrvNetWskReceiveComplete(__int64 a1, __int64 a2, KSPIN_LOCK a3)
{
  KSPIN_LOCK *v3; // rbp
  unsigned int v4; // esi
  __int64 v6; // rdi
  KIRQL v7; // al
  KSPIN_LOCK v8; // rcx
  __int64 *v9; // rdi
  KIRQL v10; // r14
  KSPIN_LOCK **v11; // rax
  __int64 v12; // rbx
  int v13; // r9d
  __int64 v14; // rax
  _QWORD *v15; // rcx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v19; // rax
  int v20; // [rsp+78h] [rbp+10h] BYREF
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF

  v3 = *(KSPIN_LOCK **)(a3 + 88);
  v4 = *(_DWORD *)(a2 + 48);
  v6 = *(unsigned int *)(a2 + 56);
  IoFreeIrp((PIRP)a2);
  if ( v4 || *(_QWORD *)(a3 + 72) != v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids,
        v4,
        v6,
        *(_DWORD *)(a3 + 72));
    }
    SrvNetDisconnectConnectionInternalEx(v3, 0);
    SrvNetFreeBuffer((unsigned __int16 *)a3);
  }
  else
  {
    *(_DWORD *)(a3 + 36) = v6;
    *(_DWORD *)(a3 + 64) = 0;
    *(_DWORD *)(a3 + 96) = 0;
    *(_QWORD *)(a3 + 88) = 0;
    v7 = KeAcquireSpinLockRaiseToDpc(v3 + 10);
    v8 = v3[11];
    v9 = (__int64 *)(v3 + 11);
    v10 = v7;
    v11 = (KSPIN_LOCK **)v3[12];
    if ( *v11 != v3 + 11 )
LABEL_24:
      __fastfail(3u);
    *(_QWORD *)a3 = v9;
    *(_QWORD *)(a3 + 8) = v11;
    *v11 = (KSPIN_LOCK *)a3;
    v3[12] = a3;
    if ( (__int64 *)v8 == v9 )
    {
      while ( 1 )
      {
        v12 = *v9;
        if ( (__int64 *)*v9 == v9 )
          break;
        v21 = 0;
        v13 = *(_DWORD *)(v12 + 96);
        v20 = 0;
        if ( *(_QWORD *)(v12 + 88) )
          break;
        *(_QWORD *)(v12 + 88) = v12;
        v14 = *(_QWORD *)v12;
        if ( *(_QWORD *)(*(_QWORD *)v12 + 8LL) != v12 )
          goto LABEL_24;
        v15 = *(_QWORD **)(v12 + 8);
        if ( *v15 != v12 )
          goto LABEL_24;
        *v15 = v14;
        *(_QWORD *)(v14 + 8) = v15;
        v16 = SrvNetCommonReceiveHandler(
                (__int64)v3,
                *(unsigned int *)(v12 + 36),
                (__int64)&v20,
                v13 & 0x40000000 | 0x420u,
                *(_QWORD *)(v12 + 24),
                v12,
                (__int64)&v21);
        if ( ((v16 + 0x80000000) & 0x80000000) != 0 || v16 == -1073741802 )
        {
          if ( v20 )
            *(_DWORD *)(v12 + 64) += v20;
          if ( *(_DWORD *)(v12 + 64) == *(_DWORD *)(v12 + 36) )
          {
            SrvNetFreeBuffer((unsigned __int16 *)v12);
          }
          else
          {
            v19 = *v9;
            if ( *(__int64 **)(*v9 + 8) != v9 )
              goto LABEL_24;
            *(_QWORD *)v12 = v19;
            *(_QWORD *)(v12 + 8) = v9;
            *(_QWORD *)(v19 + 8) = v12;
            *v9 = v12;
            if ( v16 == -1073741802 )
            {
              if ( v21 )
                SrvNetReceiveFromDataBuffer((__int64)v3, v21);
            }
          }
        }
        else if ( v16 != -1073741807 )
        {
          v17 = *v9;
          if ( *(__int64 **)(*v9 + 8) != v9 )
            goto LABEL_24;
          *(_QWORD *)v12 = v17;
          *(_QWORD *)(v12 + 8) = v9;
          *(_QWORD *)(v17 + 8) = v12;
          *v9 = v12;
        }
      }
    }
    KeReleaseSpinLock(v3 + 10, v10);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400027a0  mov     [rsp+arg_0], rbx
0x1400027a5  mov     [rsp+arg_18], rbp
0x1400027aa  push    rsi
0x1400027ab  push    rdi
0x1400027ac  push    r12
0x1400027ae  push    r14
0x1400027b0  push    r15
0x1400027b2  sub     rsp, 40h
0x1400027b6  mov     rbp, [r8+58h]
0x1400027ba  mov     rcx, rdx; Irp
0x1400027bd  mov     esi, [rdx+30h]
0x1400027c0  mov     rbx, r8
0x1400027c3  mov     edi, [rdx+38h]
0x1400027c6  call    cs:__imp_IoFreeIrp
0x1400027cd  nop     dword ptr [rax+rax+00h]
0x1400027d2  test    esi, esi
0x1400027d4  jnz     loc_14000293B
0x1400027da  cmp     [rbx+48h], rdi
0x1400027de  jnz     loc_14000293B
0x1400027e4  xor     r15d, r15d
0x1400027e7  mov     [rbx+24h], edi
0x1400027ea  lea     rcx, [rbp+50h]; SpinLock
0x1400027ee  mov     [rbx+40h], r15d
0x1400027f2  mov     [rbx+60h], r15d
0x1400027f6  mov     [rbx+58h], r15
0x1400027fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002801  nop     dword ptr [rax+rax+00h]
0x140002806  mov     rcx, [rbp+58h]
0x14000280a  lea     rdi, [rbp+58h]
0x14000280e  movzx   r14d, al
0x140002812  mov     rax, [rdi+8]
0x140002816  cmp     [rax], rdi
0x140002819  jnz     loc_1400029B7
0x14000281f  mov     [rbx], rdi
0x140002822  mov     [rbx+8], rax
0x140002826  mov     [rax], rbx
0x140002829  mov     [rdi+8], rbx
0x14000282d  cmp     rcx, rdi
0x140002830  jnz     loc_140002907
0x140002836  mov     r12d, 80000000h
0x14000283c  mov     rbx, [rdi]
0x14000283f  cmp     rbx, rdi
0x140002842  jz      loc_140002907
0x140002848  mov     [rsp+68h+arg_10], r15
0x140002850  mov     r9d, [rbx+60h]
0x140002854  mov     [rsp+68h+arg_8], r15d
0x140002859  cmp     [rbx+58h], r15
0x14000285d  jnz     loc_140002907
0x140002863  mov     [rbx+58h], rbx
0x140002867  mov     rax, [rbx]
0x14000286a  cmp     [rax+8], rbx
0x14000286e  jnz     loc_1400029B7
0x140002874  mov     rcx, [rbx+8]
0x140002878  cmp     [rcx], rbx
0x14000287b  jnz     loc_1400029B7
0x140002881  mov     [rcx], rax
0x140002884  lea     r8, [rsp+68h+arg_8]
0x140002889  mov     [rax+8], rcx
0x14000288d  and     r9d, 40000000h
0x140002894  mov     edx, [rbx+24h]
0x140002897  lea     rax, [rsp+68h+arg_10]
0x14000289f  mov     [rsp+68h+var_38], rax
0x1400028a4  or      r9d, 420h
0x1400028ab  mov     rax, [rbx+18h]
0x1400028af  mov     rcx, rbp
0x1400028b2  mov     [rsp+68h+var_40], rbx
0x1400028b7  mov     [rsp+68h+var_48], rax
0x1400028bc  call    SrvNetCommonReceiveHandler
0x1400028c1  mov     ecx, eax
0x1400028c3  add     eax, r12d
0x1400028c6  test    r12d, eax
0x1400028c9  jnz     loc_1400029A3
0x1400028cf  cmp     ecx, 0C0000016h
0x1400028d5  jz      loc_1400029A3
0x1400028db  cmp     ecx, 0C0000011h
0x1400028e1  jz      loc_14000283C
0x1400028e7  mov     rax, [rdi]
0x1400028ea  cmp     [rax+8], rdi
0x1400028ee  jnz     loc_1400029B7
0x1400028f4  mov     [rbx], rax
0x1400028f7  mov     [rbx+8], rdi
0x1400028fb  mov     [rax+8], rbx
0x1400028ff  mov     [rdi], rbx
0x140002902  jmp     loc_14000283C
0x140002907  movzx   edx, r14b; NewIrql
0x14000290b  lea     rcx, [rbp+50h]; SpinLock
0x14000290f  call    cs:__imp_KeReleaseSpinLock
0x140002916  nop     dword ptr [rax+rax+00h]
0x14000291b  mov     rbx, [rsp+68h+arg_0]
0x140002920  mov     eax, 0C0000016h
0x140002925  mov     rbp, [rsp+68h+arg_18]
0x14000292d  add     rsp, 40h
0x140002931  pop     r15
0x140002933  pop     r14
0x140002935  pop     r12
0x140002937  pop     rdi
0x140002938  pop     rsi
0x140002939  retn
0x14000293b  mov     r10, cs:WPP_GLOBAL_Control
0x140002942  lea     rax, WPP_GLOBAL_Control
0x140002949  cmp     r10, rax
0x14000294c  jnz     short loc_1400029BE
0x14000294e  xor     edx, edx
0x140002950  mov     rcx, rbp
0x140002953  call    SrvNetDisconnectConnectionInternalEx
0x140002958  mov     rcx, rbx; Entry
0x14000295b  call    SrvNetFreeBuffer
0x140002960  jmp     short loc_14000291B
0x140002962  mov     rax, [rdi]
0x140002965  cmp     [rax+8], rdi
0x140002969  jnz     short loc_1400029B7
0x14000296b  mov     [rbx], rax
0x14000296e  mov     [rbx+8], rdi
0x140002972  mov     [rax+8], rbx
0x140002976  mov     [rdi], rbx
0x140002979  cmp     ecx, 0C0000016h
0x14000297f  jnz     loc_14000283C
0x140002985  mov     rdx, [rsp+68h+arg_10]
0x14000298d  test    rdx, rdx
0x140002990  jz      loc_14000283C
0x140002996  mov     rcx, rbp
0x140002999  call    SrvNetReceiveFromDataBuffer
0x14000299e  jmp     loc_14000283C
0x1400029a3  mov     eax, [rsp+68h+arg_8]
0x1400029a7  test    eax, eax
0x1400029a9  jz      loc_14002AF42
0x1400029af  add     [rbx+40h], eax
0x1400029b2  jmp     loc_14002AF42
0x1400029b7  mov     ecx, 3
0x1400029bc  int     29h; Win8: RtlFailFast(ecx)
0x1400029be  test    dword ptr [r10+2Ch], 20000h
0x1400029c6  jz      short loc_14000294E
0x1400029c8  cmp     byte ptr [r10+29h], 1
0x1400029cd  jb      loc_14000294E
0x1400029d3  mov     eax, [rbx+48h]
0x1400029d6  lea     r8, WPP_0bd25dad6c3a3d1c3ca87626e1622cba_Traceguids
0x1400029dd  mov     rcx, [r10+18h]
0x1400029e1  mov     edx, 0Fh
0x1400029e6  mov     dword ptr [rsp+68h+var_40], eax
0x1400029ea  mov     r9d, esi
0x1400029ed  mov     dword ptr [rsp+68h+var_48], edi
0x1400029f1  call    WPP_SF_DDD
0x1400029f6  jmp     loc_14000294E
0x14002af42  mov     eax, [rbx+24h]
0x14002af45  cmp     [rbx+40h], eax
0x14002af48  jnz     loc_140002962
0x14002af4e  mov     rcx, rbx; Entry
0x14002af51  call    SrvNetFreeBuffer
0x14002af56  nop
0x14002af57  jmp     loc_14000283C
```
