# CConnection::SendPreloginPacket(ulong)

- ea: `0x38387e400`
- end: `0x38387e630`
- name: `?SendPreloginPacket@CConnection@@AEAAJK@Z`
- size: `560`
- prototype: `int(CConnection *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x38387e310`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383843870`
- `0x38387e0e0`
- `0x38387e400`
- `0x383881c10`
- `0x383881d60`
- `0x383885a60`
- `0x38391ac10`
- `0x38391aed0`
- `0x38391b040`

## import_xrefs

- `MSVCR100!strnlen` at `0x383885a11`
- `MSVCR100!strnlen` at `0x383885a11`
- `KERNEL32!TlsSetValue` at `0x38387e4dc`
- `KERNEL32!TlsSetValue` at `0x38387e4dc`
- `KERNEL32!GetCurrentThreadId` at `0x383885ac7`
- `KERNEL32!GetCurrentThreadId` at `0x383885ac7`

## pseudocode

```c
__int64 __fastcall CConnection::SendPreloginPacket(CConnection *this, unsigned int a2)
{
  __int16 v3; // r14
  int v5; // ebx
  unsigned __int16 v6; // di
  unsigned __int64 v7; // r8
  unsigned __int8 v8; // si
  unsigned __int8 *v9; // r15
  unsigned int v10; // eax
  __int64 v11; // rax
  unsigned __int16 v12; // di
  __int64 v13; // rax
  BATCHCTX *v14; // rcx
  void *v15; // rdx
  __int64 result; // rax
  unsigned __int16 v17; // r14
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  struct _GUID v21; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v22[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v23[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v24[1056]; // [rsp+110h] [rbp+10h] BYREF

  v3 = 0;
  v5 = 0;
  v6 = 31;
  memset(v24, 0, 0x41Fu);
  v8 = 0;
  while ( 1 )
  {
    if ( v6 - 31 >= 1024 )
    {
LABEL_13:
      if ( v5 < 0 )
        return (unsigned int)v5;
      v14 = (BATCHCTX *)*((_QWORD *)this + 2);
      v15 = (void *)*((_QWORD *)v14 + 12);
      v24[30] = -1;
      return BATCHCTX::QueuePacket(v14, v15, v6, v24, 0x12u, a2, 1);
    }
    v9 = &v24[4 * v8 + v8];
    *v9 = v8;
    *(_WORD *)(v9 + 1) = __ROL2__(v6, 8);
    switch ( v8 )
    {
      case 0u:
        *(_DWORD *)&v24[v6] = 1494941707;
        *(_WORD *)&v24[v6 + 4] = 0;
        v3 = 6;
        break;
      case 1u:
        v3 = 1;
        v24[v6] = *((_BYTE *)this + 404);
        break;
      case 2u:
        v17 = strnlen((const char *)this + 84, 0x100u);
        result = StringCbCopyNA((char *)&v24[v6], 1055LL - v6, (const char *)this + 84, v17);
        v5 = result;
        if ( (int)result < 0 )
          return result;
        v3 = v17 + 1;
        break;
      case 3u:
        if ( g_AllocatorInUse )
        {
          v3 = 4;
          *(_DWORD *)&v24[v6] = GetCurrentThreadId();
        }
        else
        {
          v18 = 0;
          (*(void (__fastcall **)(struct ISOSHost *, __int64 *, unsigned __int64, __int64))(*(_QWORD *)g_pISOSHost
                                                                                          + 360LL))(
            g_pISOSHost,
            &v18,
            v7,
            1);
          *(_DWORD *)&v24[v6] = v18;
          v3 = 4;
        }
        break;
      case 4u:
        v3 = 1;
        v24[v6] = (*((_DWORD *)this + 100) & 1) == 1;
        break;
      case 5u:
        if ( !(unsigned int)CActivityID::getCurrentCActivityID(&Uuid) )
          goto LABEL_25;
        if ( !TlsSetValue(g_dwCorrelationIndex, (LPVOID)(unsigned int)++v20) )
          goto LABEL_25;
        v10 = SNIGetInfo(*((struct SNI_Conn **)this + 1));
        if ( v10 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            bidTraceErr(off_383B43580[0], 2659337, v10);
LABEL_25:
            if ( (bidGblFlags & 2) != 0 && off_383B4A668[0] && bidID != -1 )
              off_383B15040();
          }
        }
        else
        {
          v11 = v6;
          v12 = v6 + 16;
          *(struct _GUID *)&v24[v11] = v21;
          v3 = 36;
          v13 = v12;
          v12 += 16;
          *(UUID *)&v24[v13] = Uuid;
          *(_DWORD *)&v24[v12] = v20;
          v6 = v12 - 32;
          if ( PrintGUID(&v21, v23, v7) && PrintGUID(&Uuid, v22, v7) && (bidGblFlags & 2) != 0 && off_383B4A670[0] )
            bidTraceW(off_383B435C0[0], 146432, off_383B4A670[0], v23);
        }
        break;
      default:
        break;
    }
    v6 += v3;
    *(_WORD *)(v9 + 3) = __ROL2__(v3, 8);
    if ( v6 > 0x41Fu )
      break;
    if ( ++v8 >= 6u )
      goto LABEL_13;
    v3 = 0;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    bidTraceW(off_383B435C0[0], 179241, off_383B49128[0], 2147549183LL);
  return 2147549183LL;
}

```

## disassembly

```asm
0x38387e400  mov     [rsp-8+arg_10], rbx
0x38387e405  mov     [rsp-8+arg_18], rsi
0x38387e40a  push    rbp
0x38387e40b  push    rdi
0x38387e40c  push    r12
0x38387e40e  push    r13
0x38387e410  push    r14
0x38387e412  lea     rbp, [rsp-440h]
0x38387e41a  sub     rsp, 540h
0x38387e421  mov     rax, cs:__security_cookie
0x38387e428  xor     rax, rsp
0x38387e42b  mov     [rbp+460h+var_30], rax
0x38387e432  mov     r13, rcx
0x38387e435  xor     r14d, r14d
0x38387e438  mov     r12d, edx
0x38387e43b  lea     rcx, [rbp+460h+var_450]; void *
0x38387e43f  mov     r8d, 41Fh; Size
0x38387e445  xor     edx, edx; Val
0x38387e447  mov     ebx, r14d
0x38387e44a  lea     edi, [r14+1Fh]
0x38387e44e  call    memset
0x38387e453  xor     sil, sil
0x38387e456  lea     rdx, cs:383800000h
0x38387e45d  lea     r9d, [r14+1]
0x38387e461  mov     [rsp+560h+arg_8], r15
0x38387e469  nop     dword ptr [rax+00000000h]
0x38387e470  movzx   eax, di
0x38387e473  sub     eax, 1Fh
0x38387e476  cmp     eax, 400h
0x38387e47b  jge     loc_38387E5CB
0x38387e481  movzx   ecx, sil
0x38387e485  lea     rax, [rbp+460h+var_450]
0x38387e489  add     rax, rcx
0x38387e48c  lea     r15, [rax+rcx*4]
0x38387e490  movzx   eax, di
0x38387e493  rol     ax, 8
0x38387e497  mov     [r15], sil
0x38387e49a  mov     [r15+1], ax
0x38387e49f  movzx   eax, sil
0x38387e4a3  cmp     eax, 5; switch 6 cases
0x38387e4a6  ja      def_38387E4B6; jumptable 000000038387E4B6 default case
0x38387e4ac  mov     ecx, ds:(jpt_38387E4B6 - 383800000h)[rdx+rax*4]
0x38387e4b3  add     rcx, rdx
0x38387e4b6  jmp     rcx; switch jump
0x38387e4b8  lea     rcx, [rsp+560h+Uuid]; jumptable 000000038387E4B6 case 5
0x38387e4bd  call    ?getCurrentCActivityID@CActivityID@@SAHQEAU1@@Z; CActivityID::getCurrentCActivityID(CActivityID * const)
0x38387e4c2  test    eax, eax
0x38387e4c4  jz      loc_383885B32
0x38387e4ca  mov     eax, [rsp+560h+var_508]
0x38387e4ce  mov     ecx, cs:?g_dwCorrelationIndex@@3KA; dwTlsIndex
0x38387e4d4  inc     eax
0x38387e4d6  mov     edx, eax; lpTlsValue
0x38387e4d8  mov     [rsp+560h+var_508], eax
0x38387e4dc  call    cs:__imp_TlsSetValue
0x38387e4e2  test    eax, eax
0x38387e4e4  jz      loc_383885B32
0x38387e4ea  mov     rcx, [r13+8]; struct SNI_Conn *
0x38387e4ee  lea     r8, [rsp+560h+var_500]
0x38387e4f3  mov     edx, 8
0x38387e4f8  call    SNIGetInfo
0x38387e4fd  test    eax, eax
0x38387e4ff  jnz     loc_383885B11
0x38387e505  movzx   eax, di
0x38387e508  add     di, 10h
0x38387e50c  lea     rcx, [rbp+460h+var_450]
0x38387e510  add     rcx, rax
0x38387e513  mov     rax, qword ptr [rsp+560h+var_500.Data1]
0x38387e518  lea     rdx, [rbp+460h+var_4A0]; unsigned __int16 *
0x38387e51c  mov     [rcx], rax
0x38387e51f  mov     rax, qword ptr [rsp+560h+var_500.Data4]
0x38387e524  mov     r14d, 24h ; '$'
0x38387e52a  mov     [rcx+8], rax
0x38387e52e  movzx   eax, di
0x38387e531  add     di, 10h
0x38387e535  lea     rcx, [rbp+460h+var_450]
0x38387e539  add     rcx, rax
0x38387e53c  mov     rax, qword ptr [rsp+560h+Uuid.Data1]
0x38387e541  mov     [rcx], rax
0x38387e544  mov     rax, qword ptr [rsp+560h+Uuid.Data4]
0x38387e549  mov     [rcx+8], rax
0x38387e54d  mov     eax, [rsp+560h+var_508]
0x38387e551  movzx   ecx, di
0x38387e554  mov     dword ptr [rbp+rcx+460h+var_450], eax
0x38387e558  mov     eax, 0FFE0h
0x38387e55d  lea     rcx, [rsp+560h+var_500]; struct _GUID *
0x38387e562  add     di, ax
0x38387e565  call    ?PrintGUID@@YAHPEBU_GUID@@PEAG_K@Z; PrintGUID(_GUID const *,ushort *,unsigned __int64)
0x38387e56a  test    eax, eax
0x38387e56c  jz      short loc_38387E58E
0x38387e56e  lea     rdx, [rsp+560h+var_4F0]; unsigned __int16 *
0x38387e573  lea     rcx, [rsp+560h+Uuid]; struct _GUID *
0x38387e578  call    ?PrintGUID@@YAHPEBU_GUID@@PEAG_K@Z; PrintGUID(_GUID const *,ushort *,unsigned __int64)
0x38387e57d  test    eax, eax
0x38387e57f  jz      short loc_38387E58E
0x38387e581  test    byte ptr cs:_bidGblFlags, 2
0x38387e588  jnz     loc_383885B8B
0x38387e58e  mov     r9d, 1
0x38387e594  lea     rdx, cs:383800000h
0x38387e59b  movzx   eax, r14w; jumptable 000000038387E4B6 default case
0x38387e59f  add     di, r14w
0x38387e5a3  rol     ax, 8
0x38387e5a7  mov     [r15+3], ax
0x38387e5ac  mov     eax, 41Fh
0x38387e5b1  cmp     di, ax
0x38387e5b4  ja      loc_383885BCE
0x38387e5ba  inc     sil
0x38387e5bd  cmp     sil, 6
0x38387e5c1  jnb     short loc_38387E5CB
0x38387e5c3  xor     r14d, r14d
0x38387e5c6  jmp     loc_38387E470
0x38387e5cb  test    ebx, ebx
0x38387e5cd  js      loc_383885C13
0x38387e5d3  mov     rcx, [r13+10h]; this
0x38387e5d7  mov     [rsp+560h+var_530], r9d; int
0x38387e5dc  lea     r9, [rbp+460h+var_450]; unsigned __int8 *
0x38387e5e0  mov     rdx, [rcx+60h]; void *
0x38387e5e4  movzx   r8d, di; unsigned __int64
0x38387e5e8  mov     [rsp+560h+var_538], r12d; unsigned int
0x38387e5ed  mov     [rbp+460h+var_432], 0FFh
0x38387e5f1  mov     [rsp+560h+var_540], 12h; unsigned __int8
0x38387e5f6  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x38387e5fb  jmp     short $+2
0x38387e5fd  mov     r15, [rsp+560h+arg_8]
0x38387e605  mov     rcx, [rbp+460h+var_30]
0x38387e60c  xor     rcx, rsp; StackCookie
0x38387e60f  call    __security_check_cookie
0x38387e614  lea     r11, [rsp+560h+var_20]
0x38387e61c  mov     rbx, [r11+40h]
0x38387e620  mov     rsi, [r11+48h]
0x38387e624  mov     rsp, r11
0x38387e627  pop     r14
0x38387e629  pop     r13
0x38387e62b  pop     r12
0x38387e62d  pop     rdi
0x38387e62e  pop     rbp
0x38387e62f  retn
0x38387d76a  movzx   eax, byte ptr [r13+194h]; jumptable 000000038387E4B6 case 1
0x38387d772  movzx   ecx, di
0x38387d775  movzx   r14d, r9w
0x38387d779  mov     [rbp+rcx+460h+var_450], al
0x38387d77d  jmp     def_38387E4B6; jumptable 000000038387E4B6 default case
0x38387d782  mov     eax, [r13+190h]; jumptable 000000038387E4B6 case 4
0x38387d789  movzx   r14d, r9w
0x38387d78d  and     al, 1
0x38387d78f  cmp     al, 1
0x38387d791  movzx   eax, di
0x38387d794  setz    cl
0x38387d797  mov     [rbp+rax+460h+var_450], cl
0x38387d79b  jmp     def_38387E4B6; jumptable 000000038387E4B6 default case
0x383885a08  lea     rcx, [r13+54h]; jumptable 000000038387E4B6 case 2
0x383885a0c  mov     edx, 100h; MaxCount
0x383885a11  call    cs:__imp_strnlen
0x383885a17  lea     rcx, [rbp+460h+var_450]
0x383885a1b  mov     edx, 41Fh
0x383885a20  movzx   r14d, ax
0x383885a24  movzx   eax, di
0x383885a27  lea     r8, [r13+54h]; char *
0x383885a2b  sub     rdx, rax; unsigned __int64
0x383885a2e  add     rcx, rax; char *
0x383885a31  mov     r9d, r14d; unsigned __int64
0x383885a34  call    ?StringCbCopyNA@@YAJPEAD_KPEBD1@Z; StringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x383885a39  mov     ebx, eax
0x383885a3b  test    eax, eax
0x383885a3d  js      loc_38387E5FD
0x383885a43  inc     r14w
0x383885a47  jmp     loc_38387E58E
0x383885abe  cmp     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, 0; jumptable 000000038387E4B6 case 3
0x383885ac5  jz      short loc_383885ADF
0x383885ac7  call    cs:__imp_GetCurrentThreadId
0x383885acd  movzx   ecx, di
0x383885ad0  mov     r14d, 4
0x383885ad6  mov     dword ptr [rbp+rcx+460h+var_450], eax
0x383885ada  jmp     loc_38387E58E
0x383885adf  xor     ecx, ecx
0x383885ae1  lea     rdx, [rsp+560h+var_520]
0x383885ae6  mov     [rsp+560h+var_520], rcx
0x383885aeb  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x383885af2  mov     rax, [rcx]
0x383885af5  call    qword ptr [rax+168h]
0x383885afb  mov     eax, dword ptr [rsp+560h+var_520]
0x383885aff  movzx   ecx, di
0x383885b02  mov     dword ptr [rbp+rcx+460h+var_450], eax
0x383885b06  mov     r14d, 4
0x383885b0c  jmp     loc_38387E58E
0x383885b11  test    byte ptr cs:_bidGblFlags, 2
0x383885b18  jz      loc_38387E58E
0x383885b1e  mov     rcx, cs:off_383B43580; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383885b25  mov     r8d, eax
0x383885b28  mov     edx, 289409h
0x383885b2d  call    _bidTraceErr
0x383885b32  test    byte ptr cs:_bidGblFlags, 2
0x383885b39  jz      loc_38387E58E
0x383885b3f  mov     rax, cs:off_383B4A668; "<CConnection::SendPreloginPacket|SNAC|E"...
0x383885b46  test    rax, rax
0x383885b49  jz      loc_38387E58E
0x383885b4f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383885b57  jz      loc_38387E58E
0x383885b5d  mov     r9, cs:off_383B4A668; "<CConnection::SendPreloginPacket|SNAC|E"...
0x383885b64  mov     rdx, cs:off_383B435C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383885b6b  xor     ecx, ecx
0x383885b6d  mov     qword ptr [rsp+560h+var_540], rcx
0x383885b72  mov     rcx, cs:_bidID
0x383885b79  mov     r8d, 27000h
0x383885b7f  call    cs:off_383B15040
0x383885b85  nop
0x383885b86  jmp     loc_38387E58E
0x383885b8b  mov     rax, cs:off_383B4A670; "<CConnection::SendPreloginPacket> PreLo"...
0x383885b92  test    rax, rax
0x383885b95  jz      loc_38387E58E
0x383885b9b  mov     eax, [rsp+560h+var_508]
0x383885b9f  mov     r8, cs:off_383B4A670; "<CConnection::SendPreloginPacket> PreLo"...
0x383885ba6  mov     rcx, cs:off_383B435C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383885bad  mov     [rsp+560h+var_538], eax
0x383885bb1  lea     rax, [rsp+560h+var_4F0]
0x383885bb6  lea     r9, [rbp+460h+var_4A0]
0x383885bba  mov     edx, 23C00h
0x383885bbf  mov     qword ptr [rsp+560h+var_540], rax
0x383885bc4  call    _bidTraceW
0x383885bc9  jmp     loc_38387E58E
0x383885bce  test    byte ptr cs:_bidGblFlags, 2
0x383885bd5  jz      short loc_383885C09
0x383885bd7  mov     rcx, cs:off_383B435C0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383885bde  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383885be5  test    rax, rax
0x383885be8  jz      short loc_383885C09
0x383885bea  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383885bf1  mov     r9d, 8000FFFFh
0x383885bf7  mov     edx, 2BC29h
0x383885bfc  mov     dword ptr [rsp+560h+var_540], 0AFh
0x383885c04  call    _bidTraceW
0x383885c09  mov     eax, 8000FFFFh
0x383885c0e  jmp     loc_38387E5FD
0x383885c13  mov     eax, ebx
0x383885c15  jmp     loc_38387E5FD
0x383885c34  movzx   eax, di; jumptable 000000038387E4B6 case 0
0x383885c37  xor     ecx, ecx
0x383885c39  mov     dword ptr [rbp+rax+460h+var_450], 591B000Bh
0x383885c41  mov     [rbp+rax+460h+var_44C], cx
0x383885c46  lea     r14d, [rcx+6]
0x383885c4a  jmp     def_38387E4B6; jumptable 000000038387E4B6 default case
```
