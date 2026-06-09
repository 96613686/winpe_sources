# TpmTransport::DispatchCommand(void *,uint,void *,uint *,int,TpmTransport::TpmTimeouts *)

- ea: `0x140009660`
- end: `0x140009cee`
- name: `?DispatchCommand@TpmTransport@@QEAAJPEAXI0PEAIHPEAVTpmTimeouts@1@@Z`
- size: `1678`
- prototype: `__int64 __fastcall(TpmTransport *__hidden this, void *, unsigned int, void *, unsigned int *, int, struct TpmTransport::TpmTimeouts *)`
- caller_count: `20`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006b70`
- `0x1400072cc`
- `0x140007b5c`
- `0x140007c90`
- `0x140008278`
- `0x140008758`
- `0x1400092bc`
- `0x140013964`
- `0x140015214`
- `0x140015a00`
- `0x140015b10`
- `0x140016228`
- `0x140016358`
- `0x140016afc`
- `0x14001d840`
- `0x140029130`
- `0x1400293bc`
- `0x140029560`
- `0x1400297f0`
- `0x1400299ec`

## callees

- `0x140009278`
- `0x140009660`
- `0x140009d00`
- `0x14001a4f0`
- `0x140039780`
- `0x140045430`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009974`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009974`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009862`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400099db`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009abf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009862`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400099db`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009abf`
- `ntoskrnl!KeReleaseMutex` at `0x1400098e7`
- `ntoskrnl!KeReleaseMutex` at `0x140009be3`
- `ntoskrnl!KeReleaseMutex` at `0x1400098e7`
- `ntoskrnl!KeReleaseMutex` at `0x140009be3`
- `ntoskrnl!bsearch` at `0x140009754`
- `ntoskrnl!bsearch` at `0x140009754`

## pseudocode

```c
__int64 __fastcall TpmTransport::DispatchCommand(
        TpmTransport *this,
        char *a2,
        unsigned int a3,
        char *a4,
        unsigned int *a5,
        int a6,
        struct TpmTransport::TpmTimeouts *a7)
{
  __int64 result; // rax
  char *v8; // r14
  int *v10; // rcx
  unsigned __int8 *v11; // rsi
  unsigned int v12; // r12d
  unsigned __int32 v13; // r12d
  __int64 v14; // r13
  unsigned int v15; // r15d
  __int16 v16; // r14
  unsigned __int32 v17; // edi
  __int16 v18; // r14
  _DWORD *v19; // rax
  char *v20; // r9
  __int64 v21; // r15
  __int64 v22; // r14
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  char v25; // dl
  __int64 v26; // rcx
  union _LARGE_INTEGER v27; // rdx
  char *v28; // rdi
  int v29; // edi
  unsigned int v30; // r15d
  unsigned int v31; // r14d
  int v32; // eax
  __int64 v33; // r8
  unsigned int v34; // ecx
  __int64 v35; // rdx
  unsigned __int32 v37; // r14d
  unsigned __int16 v38; // ax
  __int64 v39; // rdx
  unsigned __int32 Key; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-69h] BYREF
  union _LARGE_INTEGER Timeout[2]; // [rsp+58h] [rbp-61h] BYREF
  int v43; // [rsp+68h] [rbp-51h]
  int *v44; // [rsp+70h] [rbp-49h]
  unsigned __int64 v45; // [rsp+78h] [rbp-41h]
  union _LARGE_INTEGER v46; // [rsp+80h] [rbp-39h]
  PRKMUTEX Mutex; // [rsp+88h] [rbp-31h]
  __int128 v48; // [rsp+98h] [rbp-21h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 retaddr; // [rsp+100h] [rbp+47h]
  unsigned int v51; // [rsp+108h] [rbp+4Fh]
  unsigned int v53; // [rsp+118h] [rbp+5Fh]

  v53 = a3;
  result = *((unsigned int *)this + 2);
  v8 = a2;
  v41 = 0;
  if ( (int)result < 0 )
    return result;
  if ( a3 < 0xA || *a5 < 0xA )
    return 3221225485LL;
  v10 = &TpmTransport::m_DefaultTimeouts;
  v11 = 0;
  v12 = *(_DWORD *)(a2 + 6);
  if ( a7 )
    v10 = (int *)a7;
  v44 = v10;
  v13 = _byteswap_ulong(v12);
  v14 = MEMORY[0xFFFFF78000000008];
  v15 = *((_DWORD *)this + 5);
  v43 = *((_DWORD *)this + 60);
  v51 = v15;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || TpmTransportType::m_Version != 2 )
  {
LABEL_24:
    Key = 0;
    v45 = v14 + 900000000;
    v51 = v15;
    if ( !v11 )
    {
      v27.QuadPart = (LONGLONG)v8;
LABEL_26:
      v28 = (char *)this + 72;
      Mutex = (PRKMUTEX)((char *)this + 72);
      v46 = v27;
      while ( 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          Timeout[0] = v27;
          Timeout[1].QuadPart = (unsigned __int16)a3;
          v48 = *(_OWORD *)&Timeout[0].LowPart;
          WPP_SF_L_HEX_(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids,
            v13,
            (__int64)&v48);
        }
        KeWaitForSingleObject(v28, Executive, 0, 0, 0);
        v29 = (*(__int64 (__fastcall **)(TpmTransport *, char *, _QWORD, int *, int))(*(_QWORD *)this + 72LL))(
                this,
                v8,
                v53,
                v44,
                a6);
        if ( v29 < 0 )
        {
LABEL_74:
          KeReleaseMutex(Mutex, 0);
          goto LABEL_40;
        }
        v30 = 1;
LABEL_30:
        v31 = *((_DWORD *)this + 5);
        while ( 1 )
        {
          v41 = *a5;
          v32 = (*(__int64 (__fastcall **)(TpmTransport *, char *, unsigned int *, _QWORD, int *, int))(*(_QWORD *)this + 80LL))(
                  this,
                  a4,
                  &v41,
                  v30,
                  v44,
                  a6);
          v29 = v32;
          if ( !v32 )
            break;
          v30 = 0;
          if ( v32 != -2147483631 )
          {
            if ( v32 != -1073740024 )
              goto LABEL_74;
            Timeout[0].QuadPart = -10000LL * v31;
            if ( KeWaitForSingleObject((char *)this + 40, Executive, 0, 0, Timeout) == 258
              && v31 < *((_DWORD *)this + 3) )
            {
              v31 += *((_DWORD *)this + 4);
            }
            if ( *((_DWORD *)this + 16) == 2 || a6 && *((_DWORD *)this + 16) == 1 )
              goto LABEL_30;
          }
        }
        KeReleaseMutex((PRKMUTEX)((char *)this + 72), 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          Timeout[1].QuadPart = (unsigned __int16)v41;
          Timeout[0].QuadPart = (LONGLONG)a4;
          v49 = *(_OWORD *)&Timeout[0].LowPart;
          WPP_SF_L_HEX_(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            (unsigned int)WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids,
            v13,
            (__int64)&v49);
        }
        if ( *((_DWORD *)this + 8) )
          goto LABEL_34;
        v34 = v41;
        if ( v41 < 0xA )
          break;
        v35 = _byteswap_ulong(*(_DWORD *)(a4 + 6));
        if ( (_DWORD)v35 == 2314 )
        {
          if ( v13 == 323 )
            goto LABEL_35;
        }
        else if ( (_DWORD)v35 == 2339 )
        {
          if ( !v43 )
            goto LABEL_35;
          *((_DWORD *)this + 60) = 0;
        }
        else if ( (_DWORD)v35 != 2048 && (_DWORD)v35 != 2050 )
        {
          if ( (unsigned int)(v35 - 2312) > 0x1A )
            goto LABEL_35;
          v33 = 83886085;
          if ( !_bittest((const int *)&v33, v35 - 2312) )
            goto LABEL_35;
        }
        v37 = Key;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_dDd(WPP_GLOBAL_Control->AttachedDevice, v35, v33, Key, v35, v51);
        Timeout[0].QuadPart = -10000LL * v51;
        if ( KeWaitForSingleObject((char *)this + 40, Executive, 0, 0, Timeout) == 258 && v51 < *((_DWORD *)this + 3) )
          v51 += *((_DWORD *)this + 4);
        if ( MEMORY[0xFFFFF78000000008] >= v45 )
        {
LABEL_34:
          v34 = v41;
LABEL_35:
          *a5 = v34;
          goto LABEL_40;
        }
        LOWORD(a3) = v53;
        v28 = (char *)this + 72;
        v27 = v46;
        Key = v37 + 1;
        v8 = a2;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids, v41);
      v29 = -1073741434;
      goto LABEL_40;
    }
LABEL_25:
    v27.QuadPart = (LONGLONG)v11;
    goto LABEL_26;
  }
  v16 = *(_WORD *)a2;
  v17 = _byteswap_ulong(*(_DWORD *)(a2 + 6));
  Key = v17;
  v18 = __ROR2__(v16, 8);
  v19 = bsearch(
          &Key,
          Tpm20ResourceMgr::m_CommandInfoTable,
          (unsigned int)NumOfElements,
          4u,
          Tpm20Info::CommandInfoComparer);
  LOWORD(a3) = v53;
  if ( !v19 )
  {
LABEL_23:
    v8 = a2;
    goto LABEL_24;
  }
  if ( v18 == -32766 )
  {
    v21 = 4 * ((*v19 >> 25) & 7u) + 14;
    if ( v53 < (unsigned int)v21 )
    {
      v29 = -1073741811;
      goto LABEL_40;
    }
    _mm_lfence();
    v20 = a2;
    v22 = (unsigned int)v21 + _byteswap_ulong(*(_DWORD *)&a2[v21 - 4]);
  }
  else
  {
    v20 = a2;
    LODWORD(v21) = 0;
    v22 = 0;
  }
  if ( v17 == 339 || v17 == 305 )
  {
    v23 = v53;
    if ( v53 < (unsigned __int64)(v22 + 2) )
    {
      v29 = -1073741811;
      goto LABEL_40;
    }
    v38 = __ROR2__(*(_WORD *)&v20[v22], 8);
    Key = v22;
    LODWORD(v22) = v38 + v22 + 2;
  }
  else
  {
    Key = 0;
    v23 = v53;
  }
  v11 = TpmAlloc(1, v23, retaddr);
  if ( v11 )
  {
    LOWORD(a3) = v53;
    v24 = 0;
    do
    {
      if ( (unsigned int)v24 < (unsigned int)v21 || (unsigned int)v24 >= (unsigned int)v22 )
        v25 = a2[v24];
      else
        v25 = -86;
      v26 = (unsigned int)v24;
      v24 = (unsigned int)(v24 + 1);
      v11[v26] = v25;
    }
    while ( (unsigned int)v24 < v53 );
    if ( v17 == 339 || v17 == 305 )
    {
      v39 = Key;
      v8 = a2;
      Key = 0;
      v11[v39] = a2[v39];
      v11[(unsigned int)(v39 + 1)] = a2[(unsigned int)(v39 + 1)];
      v45 = v14 + 900000000;
      goto LABEL_25;
    }
    v15 = v51;
    goto LABEL_23;
  }
  v29 = -1073741670;
LABEL_40:
  if ( v11 )
    ExFreePoolWithTag(v11 - 16, 0x506D7054u);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x140009660  mov     r11, rsp
0x140009663  mov     [r11+20h], r9
0x140009667  mov     [r11+18h], r8d
0x14000966b  mov     [r11+10h], rdx
0x14000966f  push    rbp
0x140009670  push    rbx
0x140009671  push    r14
0x140009673  lea     rbp, [r11-47h]
0x140009677  sub     rsp, 0E0h
0x14000967e  mov     eax, [rcx+8]
0x140009681  mov     r14, rdx
0x140009684  mov     [rbp+3Fh+var_A8], 0
0x14000968b  mov     rbx, rcx
0x14000968e  test    eax, eax
0x140009690  js      loc_140009992
0x140009696  mov     [r11-28h], rdi
0x14000969a  cmp     r8d, 0Ah
0x14000969e  jb      loc_140009BD3
0x1400096a4  mov     rax, [rbp+3Fh+arg_20]
0x1400096a8  cmp     dword ptr [rax], 0Ah
0x1400096ab  jb      loc_140009BD3
0x1400096b1  mov     rax, [rbp+3Fh+arg_30]
0x1400096b5  lea     rcx, ?m_DefaultTimeouts@TpmTransport@@1VTpmTimeouts@1@A; TpmTransport::TpmTimeouts TpmTransport::m_DefaultTimeouts
0x1400096bc  mov     [r11-20h], rsi
0x1400096c0  xor     esi, esi
0x1400096c2  mov     [r11-30h], r12
0x1400096c6  test    rax, rax
0x1400096c9  mov     r12d, [rdx+6]
0x1400096cd  cmovnz  rcx, rax
0x1400096d1  mov     [r11-38h], r13
0x1400096d5  mov     r13, 0FFFFF78000000008h
0x1400096df  mov     [rbp+3Fh+var_88], rcx
0x1400096e3  mov     [r11-40h], r15
0x1400096e7  bswap   r12d
0x1400096ea  mov     r13, [r13+0]
0x1400096ee  mov     eax, [rbx+0F0h]
0x1400096f4  mov     r15d, [rbx+14h]
0x1400096f8  mov     [rbp+3Fh+var_90], eax
0x1400096fb  mov     rax, cs:WPP_GLOBAL_Control
0x140009702  mov     [rbp+3Fh+arg_0], r15d
0x140009706  mov     ecx, [rax+2Ch]
0x140009709  test    cl, 10h
0x14000970c  jz      loc_140009805
0x140009712  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 2; TpmTransportType::VERSION TpmTransportType::m_Version
0x140009719  jnz     loc_140009805
0x14000971f  mov     edi, [rdx+6]
0x140009722  lea     rax, ?CommandInfoComparer@Tpm20Info@@CAHPEBX0@Z; Tpm20Info::CommandInfoComparer(void const *,void const *)
0x140009729  movzx   r14d, word ptr [rdx]
0x14000972d  lea     rcx, [rbp+3Fh+Key]; Key
0x140009731  mov     r8d, cs:NumOfElements; NumOfElements
0x140009738  mov     r9d, 4; SizeOfElements
0x14000973e  mov     rdx, cs:?m_CommandInfoTable@Tpm20ResourceMgr@@0PEBT_TPM20_CMD_INFO@@EB; Base
0x140009745  bswap   edi
0x140009747  mov     [rbp+3Fh+Key], edi
0x14000974a  ror     r14w, 8
0x14000974f  mov     [rsp+0F0h+PtFuncCompare], rax; PtFuncCompare
0x140009754  call    cs:__imp_bsearch
0x14000975b  nop     dword ptr [rax+rax+00h]
0x140009760  mov     r8d, dword ptr [rbp+3Fh+arg_10]
0x140009764  test    rax, rax
0x140009767  jz      loc_140009801
0x14000976d  mov     ecx, 8002h
0x140009772  cmp     r14w, cx
0x140009776  jz      loc_140009BF4
0x14000977c  mov     r9, [rbp+3Fh+arg_8]
0x140009780  xor     r15d, r15d
0x140009783  xor     r14d, r14d
0x140009786  cmp     edi, 153h
0x14000978c  jz      loc_140009B9D
0x140009792  cmp     edi, 131h
0x140009798  jz      loc_140009B9D
0x14000979e  mov     [rbp+3Fh+Key], esi
0x1400097a1  mov     edx, r8d; unsigned __int64
0x1400097a4  mov     r8, [rbp+47h]; unsigned __int64
0x1400097a8  mov     cl, 1; bool
0x1400097aa  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x1400097af  mov     rsi, rax
0x1400097b2  test    rax, rax
0x1400097b5  jz      loc_140009CE4
0x1400097bb  mov     r8d, dword ptr [rbp+3Fh+arg_10]
0x1400097bf  xor     eax, eax
0x1400097c1  mov     r9, [rbp+3Fh+arg_8]
0x1400097c5  cmp     eax, r15d
0x1400097c8  jb      loc_140009BC9
0x1400097ce  cmp     eax, r14d
0x1400097d1  jnb     loc_140009BC9
0x1400097d7  mov     dl, 0AAh
0x1400097d9  mov     ecx, eax
0x1400097db  inc     eax
0x1400097dd  mov     [rcx+rsi], dl
0x1400097e0  cmp     eax, r8d
0x1400097e3  jb      short loc_1400097C5
0x1400097e5  cmp     edi, 153h
0x1400097eb  jz      loc_140009C9D
0x1400097f1  cmp     edi, 131h
0x1400097f7  jz      loc_140009C9D
0x1400097fd  mov     r15d, [rbp+3Fh+arg_0]
0x140009801  mov     r14, [rbp+3Fh+arg_8]
0x140009805  mov     [rbp+3Fh+Key], 0
0x14000980c  lea     rax, [r13+35A4E900h]
0x140009813  mov     [rbp+3Fh+var_80], rax
0x140009817  mov     [rbp+3Fh+arg_0], r15d
0x14000981b  test    rsi, rsi
0x14000981e  jz      loc_140009C2E
0x140009824  mov     rdx, rsi
0x140009827  mov     r13, [rbp+3Fh+arg_20]
0x14000982b  lea     rdi, [rbx+48h]
0x14000982f  mov     [rbp+3Fh+Mutex], rdi
0x140009833  mov     [rbp+3Fh+var_78], rdx
0x140009837  lea     rax, WPP_GLOBAL_Control
0x14000983e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009845  cmp     rcx, rax
0x140009848  jnz     loc_140009B53
0x14000984e  xor     r9d, r9d; Alertable
0x140009851  mov     [rsp+0F0h+PtFuncCompare], 0; Timeout
0x14000985a  xor     r8d, r8d; WaitMode
0x14000985d  xor     edx, edx; WaitReason
0x14000985f  mov     rcx, rdi; Object
0x140009862  call    cs:__imp_KeWaitForSingleObject
0x140009869  nop     dword ptr [rax+rax+00h]
0x14000986e  mov     rax, [rbx]
0x140009871  mov     rdx, r14
0x140009874  mov     ecx, [rbp+3Fh+arg_28]
0x140009877  mov     r9, [rbp+3Fh+var_88]
0x14000987b  mov     r8d, dword ptr [rbp+3Fh+arg_10]
0x14000987f  mov     rax, [rax+48h]
0x140009883  mov     dword ptr [rsp+0F0h+PtFuncCompare], ecx
0x140009887  mov     rcx, rbx
0x14000988a  call    _guard_dispatch_icall
0x14000988f  mov     edi, eax
0x140009891  test    eax, eax
0x140009893  js      loc_140009BDD
0x140009899  mov     r15d, 1
0x14000989f  mov     r14d, [rbx+14h]
0x1400098a3  mov     eax, [r13+0]
0x1400098a7  lea     r8, [rbp+3Fh+var_A8]
0x1400098ab  mov     ecx, [rbp+3Fh+arg_28]
0x1400098ae  mov     r9d, r15d
0x1400098b1  mov     r15, [rbp+3Fh+arg_18]
0x1400098b5  mov     [rsp+28h], ecx
0x1400098b9  mov     rdx, r15
0x1400098bc  mov     rcx, [rbp+3Fh+var_88]
0x1400098c0  mov     [rbp+3Fh+var_A8], eax
0x1400098c3  mov     rax, [rbx]
0x1400098c6  mov     [rsp+0F0h+PtFuncCompare], rcx
0x1400098cb  mov     rcx, rbx
0x1400098ce  mov     rax, [rax+50h]
0x1400098d2  call    _guard_dispatch_icall
0x1400098d7  mov     edi, eax
0x1400098d9  test    eax, eax
0x1400098db  jnz     loc_14000999F
0x1400098e1  xor     edx, edx; Wait
0x1400098e3  lea     rcx, [rbx+48h]; Mutex
0x1400098e7  call    cs:__imp_KeReleaseMutex
0x1400098ee  nop     dword ptr [rax+rax+00h]
0x1400098f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400098fa  lea     r14, WPP_GLOBAL_Control
0x140009901  cmp     rcx, r14
0x140009904  jnz     loc_140009B06
0x14000990a  cmp     dword ptr [rbx+20h], 0
0x14000990e  jz      loc_140009A1F
0x140009914  mov     ecx, [rbp+3Fh+var_A8]
0x140009917  mov     [r13+0], ecx
0x14000991b  jmp     short loc_14000994E
0x14000991d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009924  cmp     r10, r14
0x140009927  jz      short loc_140009949
0x140009929  mov     eax, [r10+2Ch]
0x14000992d  test    al, 1
0x14000992f  jz      short loc_140009949
0x140009931  mov     r9d, ecx
0x140009934  lea     r8, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids
0x14000993b  mov     rcx, [r10+18h]
0x14000993f  mov     edx, 0Ch
0x140009944  call    WPP_SF_d
0x140009949  mov     edi, 0C0000186h
0x14000994e  mov     r15, [rsp+0F0h+var_38]
0x140009956  mov     r13, [rsp+0F0h+var_30]
0x14000995e  mov     r12, [rsp+0F0h+var_28]
0x140009966  test    rsi, rsi
0x140009969  jz      short loc_140009980
0x14000996b  lea     rcx, [rsi-10h]; P
0x14000996f  mov     edx, 506D7054h; Tag
0x140009974  call    cs:__imp_ExFreePoolWithTag
0x14000997b  nop     dword ptr [rax+rax+00h]
0x140009980  mov     rsi, [rsp+0D8h]
0x140009988  mov     eax, edi
0x14000998a  mov     rdi, [rsp+0F0h+var_20]
0x140009992  add     rsp, 0E0h
0x140009999  pop     r14
0x14000999b  pop     rbx
0x14000999c  pop     rbp
0x14000999d  retn
0x14000999f  xor     r15d, r15d
0x1400099a2  cmp     eax, 80000011h
0x1400099a7  jz      loc_1400098A3
0x1400099ad  cmp     eax, 0C0000708h
0x1400099b2  jnz     loc_140009BDD
0x1400099b8  mov     eax, r14d
0x1400099bb  xor     r9d, r9d; Alertable
0x1400099be  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1400099c5  lea     rax, [rbp+3Fh+Timeout]
0x1400099c9  xor     r8d, r8d; WaitMode
0x1400099cc  mov     qword ptr [rbp+3Fh+Timeout], rcx
0x1400099d0  xor     edx, edx; WaitReason
0x1400099d2  lea     rcx, [rbx+28h]; Object
0x1400099d6  mov     [rsp+0F0h+PtFuncCompare], rax; Timeout
0x1400099db  call    cs:__imp_KeWaitForSingleObject
0x1400099e2  nop     dword ptr [rax+rax+00h]
0x1400099e7  cmp     eax, 102h
0x1400099ec  jnz     short loc_1400099F8
0x1400099ee  cmp     r14d, [rbx+0Ch]
0x1400099f2  jnb     short loc_1400099F8
0x1400099f4  add     r14d, [rbx+10h]
0x1400099f8  mov     eax, [rbx+40h]
0x1400099fb  cmp     eax, 2
0x1400099fe  jz      loc_14000989F
0x140009a04  cmp     [rbp+3Fh+arg_28], r15d
0x140009a08  jz      loc_1400098A3
0x140009a0e  mov     eax, [rbx+40h]
0x140009a11  cmp     eax, 1
0x140009a14  jz      loc_14000989F
0x140009a1a  jmp     loc_1400098A3
0x140009a1f  mov     ecx, [rbp+3Fh+var_A8]
0x140009a22  cmp     ecx, 0Ah
0x140009a25  jb      loc_14000991D
0x140009a2b  mov     edx, [r15+6]
0x140009a2f  bswap   edx
0x140009a31  mov     eax, edx
0x140009a33  sub     eax, 90Ah
0x140009a38  jz      loc_140009C8B
0x140009a3e  cmp     eax, 19h
0x140009a41  jz      loc_140009C72
0x140009a47  cmp     edx, 800h
0x140009a4d  jz      loc_140009C24
0x140009a53  cmp     edx, 802h
0x140009a59  jz      loc_140009C24
0x140009a5f  lea     eax, [rdx-908h]
0x140009a65  cmp     eax, 1Ah
0x140009a68  ja      short loc_140009A7A
0x140009a6a  mov     r8d, 5000005h
0x140009a70  bt      r8d, eax
0x140009a74  jb      loc_140009C24
0x140009a7a  xor     eax, eax
0x140009a7c  test    eax, eax
0x140009a7e  jz      loc_140009917
0x140009a84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009a8b  mov     r15d, [rbp+3Fh+arg_0]
0x140009a8f  cmp     rcx, r14
0x140009a92  mov     r14d, [rbp+3Fh+Key]
0x140009a96  jnz     loc_140009C36
0x140009a9c  mov     eax, r15d
0x140009a9f  xor     r9d, r9d; Alertable
0x140009aa2  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x140009aa9  lea     rax, [rbp+3Fh+Timeout]
0x140009aad  xor     r8d, r8d; WaitMode
0x140009ab0  mov     qword ptr [rbp+3Fh+Timeout], rcx
0x140009ab4  xor     edx, edx; WaitReason
0x140009ab6  lea     rcx, [rbx+28h]; Object
0x140009aba  mov     [rsp+0F0h+PtFuncCompare], rax; Timeout
0x140009abf  call    cs:__imp_KeWaitForSingleObject
0x140009ac6  nop     dword ptr [rax+rax+00h]
0x140009acb  cmp     eax, 102h
0x140009ad0  jz      loc_140009C5B
0x140009ad6  mov     rax, ds:0FFFFF78000000008h
0x140009ae0  cmp     rax, [rbp+3Fh+var_80]
0x140009ae4  jnb     loc_140009914
0x140009aea  mov     r8d, dword ptr [rbp+3Fh+arg_10]
0x140009aee  lea     rdi, [rbx+48h]
0x140009af2  mov     rdx, [rbp+3Fh+var_78]
0x140009af6  inc     r14d
0x140009af9  mov     [rbp+3Fh+Key], r14d
0x140009afd  mov     r14, [rbp+3Fh+arg_8]
0x140009b01  jmp     loc_140009837
0x140009b06  mov     eax, [rcx+2Ch]
0x140009b09  test    al, 10h
0x140009b0b  jz      loc_14000990A
0x140009b11  movzx   eax, word ptr [rbp+3Fh+var_A8]
0x140009b15  lea     r8, WPP_4f0e515b59eb355e214a9e7464b4de01_Traceguids
0x140009b1c  xorps   xmm0, xmm0
0x140009b1f  mov     edx, 0Bh
0x140009b24  movups  xmmword ptr [rbp+3Fh+Timeout], xmm0
0x140009b28  mov     word ptr [rbp+3Fh+Timeout+8], ax
0x140009b2c  mov     r9d, r12d
0x140009b2f  lea     rax, [rbp+3Fh+var_50]
0x140009b33  mov     qword ptr [rbp+3Fh+Timeout], r15
0x140009b37  movaps  xmm0, xmmword ptr [rbp+3Fh+Timeout]
0x140009b3b  movdqa  [rbp+3Fh+var_50], xmm0
0x140009b40  mov     rcx, [rcx+18h]
0x140009b44  mov     [rsp+0F0h+PtFuncCompare], rax
0x140009b49  call    WPP_SF_L_HEX_
0x140009b4e  jmp     loc_14000990A
0x140009b53  mov     eax, [rcx+2Ch]
0x140009b56  test    al, 10h
0x140009b58  jz      loc_14000984E
0x140009b5e  xorps   xmm0, xmm0
0x140009b61  lea     rax, [rbp+3Fh+var_60]
0x140009b65  movups  xmmword ptr [rbp+3Fh+Timeout], xmm0
0x140009b69  mov     qword ptr [rbp+3Fh+Timeout], rdx
0x140009b6d  mov     r9d, r12d
  ... truncated ...
```
