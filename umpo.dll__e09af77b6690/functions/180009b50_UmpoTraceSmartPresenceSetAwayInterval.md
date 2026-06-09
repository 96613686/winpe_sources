# UmpoTraceSmartPresenceSetAwayInterval

- ea: `0x180009b50`
- end: `0x180009d84`
- name: `UmpoTraceSmartPresenceSetAwayInterval`
- size: `564`
- prototype: `char __fastcall(char, __int64, char, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008c80`
- `0x1800098e4`

## callees

- `0x180009b50`
- `0x18000c04c`
- `0x18000d6cc`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009be1`
- `ntdll!RtlAllocateHeap` at `0x180009be1`
- `ntdll!RtlLengthSid` at `0x180009cec`
- `ntdll!RtlLengthSid` at `0x180009cec`
- `ntdll!RtlFreeHeap` at `0x180009d5e`
- `ntdll!RtlFreeHeap` at `0x180009d5e`
- `ntdll!EtwEventWrite` at `0x180009d4c`
- `ntdll!EtwEventWrite` at `0x180009d4c`

## pseudocode

```c
char __fastcall UmpoTraceSmartPresenceSetAwayInterval(char a1, __int64 a2, char a3, char a4)
{
  unsigned __int8 *v4; // rdi
  unsigned int v5; // edx
  _QWORD *v7; // r13
  int v10; // esi
  _BYTE *Heap; // rax
  _BYTE *v12; // rbx
  __int64 i; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  char v16; // al
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 *v22; // rdx
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v25; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v28; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+5Ch] [rbp-A4h]
  unsigned int *v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  _BYTE *v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+7Ch] [rbp-84h]
  int *v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B8h] [rbp-48h]
  int v41; // [rsp+BCh] [rbp-44h]
  __int16 *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  _BYTE *v44; // [rsp+D0h] [rbp-30h]
  int v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+DCh] [rbp-24h]
  int *v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+E8h] [rbp-18h]

  v4 = (unsigned __int8 *)UmpoNullSid;
  v5 = UmpoSmartPresenceAwayTimeCount;
  v7 = UmpoSmartPresenceAwayTime;
  v26 = UmpoSmartPresenceAwayTimeCount;
  v25 = 0;
  v24 = 0;
  if ( !UmpoNullSid )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v5 = v26;
  }
  if ( v5 > 0xFFFF )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v5 = v26;
  }
  v10 = 17 * v5;
  v25 = v5;
  v24 = 0;
  Heap = RtlAllocateHeap(UmpoHeapHandle, 8u, 17 * v5);
  v12 = Heap;
  if ( Heap )
  {
    for ( i = 0; (unsigned int)i < v26; *(_QWORD *)&v12[v15 + 8] = v7[v14 + 2] / 0xAuLL )
    {
      v14 = 3 * i;
      v15 = 17LL * (unsigned int)i;
      v16 = v7[3 * i];
      i = (unsigned int)(i + 1);
      v12[v15 + 16] = v16;
      *(_QWORD *)&v12[v15] = v7[v14 + 1] / 0xAuLL;
    }
    v17 = v24;
    if ( a3 )
    {
      v17 = v24 | 1;
      v24 |= 1u;
    }
    if ( a4 )
      v24 = v17 | 2;
    if ( !a1 && (unsigned int)dword_180024190 > 5 && tlgKeywordOn() )
    {
      v21 = v4[1];
      v39 = v4;
      v41 = 0;
      v43 = 2;
      v44 = v12;
      v40 = 4 * v21 + 8;
      v42 = &v25;
      v27 = v24;
      v47 = &v27;
      v45 = v10;
      v46 = 0;
      v48 = 4;
      tlgWriteTransfer_EventWriteTransfer(v18, (unsigned __int8 *)&dword_18001FB5C, v19, v20, 6u, &v38);
    }
    v29 = RtlLengthSid(v4);
    v31 = &v26;
    v36 = &v24;
    v28 = v4;
    v22 = UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_RUNDOWN;
    v30 = 0;
    v32 = 4;
    v33 = v12;
    v34 = v10;
    v35 = 0;
    v37 = 4;
    if ( !a1 )
      v22 = UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_SET;
    EtwEventWrite(UmpoProviderHandle, v22, 4, &v28);
    LOBYTE(Heap) = RtlFreeHeap(UmpoHeapHandle, 0, v12);
  }
  return (char)Heap;
}

```

## disassembly

```asm
0x180009b50  push    rbp
0x180009b52  push    rbx
0x180009b53  push    rsi
0x180009b54  push    rdi
0x180009b55  push    r12
0x180009b57  push    r13
0x180009b59  push    r14
0x180009b5b  push    r15
0x180009b5d  lea     rbp, [rsp-8]
0x180009b62  sub     rsp, 108h
0x180009b69  mov     rax, cs:__security_cookie
0x180009b70  xor     rax, rsp
0x180009b73  mov     [rbp+40h+var_50], rax
0x180009b77  mov     rdi, cs:UmpoNullSid
0x180009b7e  xor     eax, eax
0x180009b80  mov     edx, cs:UmpoSmartPresenceAwayTimeCount
0x180009b86  mov     r12b, r9b
0x180009b89  mov     r13, cs:UmpoSmartPresenceAwayTime
0x180009b90  mov     r15b, r8b
0x180009b93  mov     [rsp+140h+var_108], edx
0x180009b97  mov     r14b, cl
0x180009b9a  mov     [rsp+140h+var_10C], ax
0x180009b9f  mov     [rsp+140h+var_110], eax
0x180009ba3  test    rdi, rdi
0x180009ba6  jnz     short loc_180009BB1
0x180009ba8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009bad  mov     edx, [rsp+140h+var_108]
0x180009bb1  cmp     edx, 0FFFFh
0x180009bb7  jbe     short loc_180009BC2
0x180009bb9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009bbe  mov     edx, [rsp+140h+var_108]
0x180009bc2  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180009bc9  imul    esi, edx, 11h
0x180009bcc  mov     [rsp+140h+var_10C], dx
0x180009bd1  mov     edx, 8; Flags
0x180009bd6  mov     [rsp+140h+var_110], 0
0x180009bde  mov     r8d, esi; Size
0x180009be1  call    cs:__imp_RtlAllocateHeap
0x180009be7  mov     rbx, rax
0x180009bea  test    rax, rax
0x180009bed  jz      loc_180009D64
0x180009bf3  xor     r9d, r9d
0x180009bf6  cmp     [rsp+140h+var_108], r9d
0x180009bfb  jbe     short loc_180009C47
0x180009bfd  mov     r10, 0CCCCCCCCCCCCCCCDh
0x180009c07  mov     eax, r9d
0x180009c0a  lea     rcx, [r9+r9*2]
0x180009c0e  imul    r8, rax, 11h
0x180009c12  mov     al, [r13+rcx*8+0]
0x180009c17  inc     r9d
0x180009c1a  mov     [r8+rbx+10h], al
0x180009c1f  mov     rax, r10
0x180009c22  mul     qword ptr [r13+rcx*8+8]
0x180009c27  mov     rax, r10
0x180009c2a  shr     rdx, 3
0x180009c2e  mov     [r8+rbx], rdx
0x180009c32  mul     qword ptr [r13+rcx*8+10h]
0x180009c37  shr     rdx, 3
0x180009c3b  mov     [r8+rbx+8], rdx
0x180009c40  cmp     r9d, [rsp+140h+var_108]
0x180009c45  jb      short loc_180009C07
0x180009c47  mov     eax, [rsp+140h+var_110]
0x180009c4b  xor     r13d, r13d
0x180009c4e  test    r15b, r15b
0x180009c51  jz      short loc_180009C5A
0x180009c53  or      eax, 1
0x180009c56  mov     [rsp+140h+var_110], eax
0x180009c5a  test    r12b, r12b
0x180009c5d  jz      short loc_180009C66
0x180009c5f  or      eax, 2
0x180009c62  mov     [rsp+140h+var_110], eax
0x180009c66  mov     r15d, 4
0x180009c6c  test    r14b, r14b
0x180009c6f  jnz     short loc_180009CE9
0x180009c71  mov     eax, cs:dword_180024190
0x180009c77  cmp     eax, 5
0x180009c7a  jbe     short loc_180009CE9
0x180009c7c  call    _tlgKeywordOn
0x180009c81  test    al, al
0x180009c83  jz      short loc_180009CE9
0x180009c85  movzx   eax, byte ptr [rdi+1]
0x180009c89  lea     rdx, dword_18001FB5C; int
0x180009c90  mov     [rbp+40h+var_90], rdi
0x180009c94  mov     [rbp+40h+var_84], r13d
0x180009c98  mov     [rbp+40h+var_78], 2
0x180009ca0  lea     eax, ds:8[rax*4]
0x180009ca7  mov     [rbp+40h+var_70], rbx
0x180009cab  mov     [rbp+40h+var_88], eax
0x180009cae  lea     rax, [rsp+140h+var_10C]
0x180009cb3  mov     [rbp+40h+var_80], rax
0x180009cb7  mov     eax, [rsp+140h+var_110]
0x180009cbb  mov     [rsp+140h+var_100], eax
0x180009cbf  lea     rax, [rsp+140h+var_100]
0x180009cc4  mov     [rbp+40h+var_60], rax
0x180009cc8  lea     rax, [rbp+40h+var_B0]
0x180009ccc  mov     [rsp+140h+var_118], rax; __int64
0x180009cd1  mov     [rsp+140h+var_120], 6; ULONG
0x180009cd9  mov     [rbp+40h+var_68], esi
0x180009cdc  mov     [rbp+40h+var_64], r13d
0x180009ce0  mov     [rbp+40h+var_58], r15
0x180009ce4  call    _tlgWriteTransfer_EventWriteTransfer
0x180009ce9  mov     rcx, rdi; Sid
0x180009cec  call    cs:__imp_RtlLengthSid
0x180009cf2  mov     rcx, cs:UmpoProviderHandle
0x180009cf9  lea     r9, [rsp+140h+var_F0]
0x180009cfe  mov     [rsp+140h+var_E8], eax
0x180009d02  lea     rax, [rsp+140h+var_108]
0x180009d07  mov     [rsp+140h+var_E0], rax
0x180009d0c  lea     rax, [rsp+140h+var_110]
0x180009d11  mov     [rbp+40h+var_C0], rax
0x180009d15  mov     r8d, r15d
0x180009d18  mov     [rsp+140h+var_F0], rdi
0x180009d1d  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_RUNDOWN
0x180009d24  mov     [rsp+140h+var_E4], r13d
0x180009d29  mov     [rsp+140h+var_D8], r15
0x180009d2e  mov     [rsp+140h+var_D0], rbx
0x180009d33  mov     [rsp+140h+var_C8], esi
0x180009d37  mov     [rsp+140h+var_C4], r13d
0x180009d3c  mov     [rbp+40h+var_B8], r15
0x180009d40  test    r14b, r14b
0x180009d43  jnz     short loc_180009D4C
0x180009d45  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_SET
0x180009d4c  call    cs:__imp_EtwEventWrite
0x180009d52  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180009d59  mov     r8, rbx; P
0x180009d5c  xor     edx, edx; Flags
0x180009d5e  call    cs:__imp_RtlFreeHeap
0x180009d64  mov     rcx, [rbp+40h+var_50]
0x180009d68  xor     rcx, rsp; StackCookie
0x180009d6b  call    __security_check_cookie
0x180009d70  add     rsp, 108h
0x180009d77  pop     r15
0x180009d79  pop     r14
0x180009d7b  pop     r13
0x180009d7d  pop     r12
0x180009d7f  pop     rdi
0x180009d80  pop     rsi
0x180009d81  pop     rbx
0x180009d82  pop     rbp
0x180009d83  retn
```
