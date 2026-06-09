# TpmTransportTis::SubmitCommand(void *,uint,TpmTransport::TpmTimeouts *,int)

- ea: `0x1400183d0`
- end: `0x14001887c`
- name: `?SubmitCommand@TpmTransportTis@@UEAAJPEAXIPEAVTpmTimeouts@TpmTransport@@H@Z`
- size: `1196`
- prototype: `__int64 __usercall@<rax>(TpmTransportTis *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, struct TpmTransport::TpmTimeouts *@<r9>, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140001620`
- `0x140001880`
- `0x1400052b0`
- `0x1400078b8`
- `0x14000ff70`
- `0x1400103f8`
- `0x140016ac4`
- `0x1400183d0`
- `0x14001a770`
- `0x14001b1ac`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001841e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001841e`
- `ntoskrnl!KeReleaseMutex` at `0x140018855`
- `ntoskrnl!KeReleaseMutex` at `0x140018855`

## pseudocode

```c
__int64 __fastcall TpmTransportTis::SubmitCommand(
        TpmTransportTis *this,
        _BYTE *a2,
        unsigned int a3,
        struct TpmTransport::TpmTimeouts *a4,
        int a5)
{
  int v7; // esi
  char v8; // r15
  char v9; // al
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ebx
  unsigned int v14; // r12d
  __int16 v15; // bx
  bool v16; // zf
  _BYTE *v17; // r14
  unsigned int v18; // esi
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // r9d
  int Timeout; // [rsp+20h] [rbp-40h]
  int v28; // [rsp+28h] [rbp-38h]
  int v29; // [rsp+28h] [rbp-38h]
  __int64 v30; // [rsp+50h] [rbp-10h] BYREF
  __int64 v31; // [rsp+58h] [rbp-8h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+40h] BYREF
  _BYTE *v33; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v34; // [rsp+B0h] [rbp+50h] BYREF

  v34 = a3;
  v33 = a2;
  if ( a3 <= *((_DWORD *)this + 90) )
  {
    KeWaitForSingleObject((char *)this + 128, Executive, 0, 0, 0);
    v16 = a5 == 0;
    *((_DWORD *)this + 79) = a5;
    v8 = !v16;
    if ( TpmTransport::ShouldCancelCommand(this, !v16) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
      if ( LODWORD(WPP_MAIN_CB.DeviceExtension) == 1 )
        v7 = -1071050751;
      else
        v7 = -1073741536;
    }
    else
    {
      v9 = TpmRegister<unsigned char>::Read((char *)this + 320);
      LOBYTE(v32) = v9;
      if ( v9 >= -1 || (v9 & 0x40) != 0 )
      {
        if ( (TPMEnableBits & 1) != 0 )
          McTemplateK0dqq_EtwWriteTransfer(v11, (const EVENT_DESCRIPTOR *)TPM_HW_STATE_ERROR, v12, 44, 110, v9);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids,
            *((unsigned int *)this + 80));
        v7 = -1073741436;
      }
      else if ( (v9 & 0x20) != 0
             || (LOBYTE(v12) = 2,
                 TpmRegister<unsigned char>::Write((char *)this + 320, v10, v12),
                 v7 = TpmTransportTis::WaitForBitSet<unsigned char>(this, 32, v28, *(_DWORD *)a4, v8, 0, 1),
                 v7 >= 0) )
      {
        v13 = 0;
        while ( 1 )
        {
          LOBYTE(v12) = 64;
          TpmRegister<unsigned char>::Write((char *)this + 324, v10, v12);
          v7 = TpmTransportTis::WaitForBitSet<unsigned char>(this, 64, v28, *((_DWORD *)a4 + 1), v8, 0, 1);
          if ( v7 >= 0 )
            break;
          if ( v13
            || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          {
            if ( (unsigned int)++v13 >= 2 )
              goto LABEL_51;
          }
          else
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
            v13 = 1;
          }
        }
        if ( LODWORD(WPP_MAIN_CB.DeviceExtension) == 6 )
          TpmRegister<unsigned char>::Write((char *)this + 336, v10, 0);
        *((_DWORD *)this + 78) = 1;
        LOWORD(v30) = 0;
        v14 = 0;
        v31 = MEMORY[0xFFFFF78000000014];
        while ( 1 )
        {
          v7 = TpmTransportTis::WaitForBitSet<unsigned short>(
                 this,
                 Timeout,
                 v28,
                 *((_DWORD *)a4 + 2),
                 v8,
                 (__int64)&v30);
          if ( v7 < 0 )
            break;
          v15 = v30;
          v16 = (_WORD)v30 == 0;
          if ( (_WORD)v30 )
          {
            v17 = v33;
            v18 = v34 - 1;
            do
            {
              if ( v14 >= v18 )
                break;
              v19 = v14;
              LOBYTE(v19) = v17[v14];
              TpmRegister<unsigned char>::Write((char *)this + 328, 0, v19);
              ++v14;
              --v15;
            }
            while ( v15 );
            LOWORD(v30) = v15;
            v16 = v15 == 0;
          }
          if ( !v16 )
          {
            v7 = TpmTransportTis::WaitForBitSet<unsigned char>(this, 136, v28, *((_DWORD *)a4 + 2), v8, 0, 1);
            if ( v7 >= 0 )
            {
              v21 = v14;
              LOBYTE(v21) = v33[v14];
              TpmRegister<unsigned char>::Write((char *)this + 328, v20, v21);
              v7 = TpmTransportTis::WaitForBitSet<unsigned char>(
                     this,
                     128,
                     v29,
                     *((_DWORD *)a4 + 2),
                     v8,
                     (__int64)&v32,
                     1);
              if ( v7 >= 0 )
              {
                v24 = MEMORY[0xFFFFF78000000014];
                if ( (unsigned int)dword_1400470A0 > 5
                  && (unsigned __int8)tlgKeywordOn(v23, v22, MEMORY[0xFFFFF78000000014], 0) )
                {
                  v33 = (_BYTE *)(v24 - v31);
                  v34 = v25;
                  v31 = 0x1000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                    v23,
                    (unsigned int)&byte_140041CAF,
                    (_DWORD)v33,
                    v25,
                    (__int64)&v31,
                    (__int64)&v34,
                    (__int64)&v33);
                }
                if ( (v32 & 8) != 0 )
                {
                  if ( (TPMEnableBits & 1) != 0 )
                    McTemplateK0dqq_EtwWriteTransfer(v23, (const EVENT_DESCRIPTOR *)TPM_HW_STATE_ERROR, v24, 44, 5, v32);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
                  }
                  v7 = -1073741436;
                }
                else
                {
                  LOBYTE(v24) = 32;
                  TpmRegister<unsigned char>::Write((char *)this + 324, v22, v24);
                  *((_QWORD *)this + 44) = MEMORY[0xFFFFF78000000014] + 10000LL * *((unsigned int *)a4 + 4);
                }
              }
            }
            break;
          }
        }
      }
    }
LABEL_51:
    KeReleaseMutex((PRKMUTEX)((char *)this + 128), 0);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400183d0  mov     [rsp-38h+arg_18], rbx
0x1400183d5  mov     [rsp-38h+arg_10], r8d
0x1400183da  mov     [rsp-38h+arg_8], rdx
0x1400183df  push    rbp
0x1400183e0  push    rsi
0x1400183e1  push    rdi
0x1400183e2  push    r12
0x1400183e4  push    r13
0x1400183e6  push    r14
0x1400183e8  push    r15
0x1400183ea  mov     rbp, rsp
0x1400183ed  sub     rsp, 60h
0x1400183f1  mov     r13, r9
0x1400183f4  mov     rdi, rcx
0x1400183f7  cmp     r8d, [rcx+168h]
0x1400183fe  jbe     short loc_14001840A
0x140018400  mov     esi, 0C000000Dh
0x140018405  jmp     loc_140018861
0x14001840a  xor     r14d, r14d
0x14001840d  sub     rcx, 0FFFFFFFFFFFFFF80h; Object
0x140018411  xor     r9d, r9d; Alertable
0x140018414  mov     [rsp+60h+Timeout], r14; Timeout
0x140018419  xor     r8d, r8d; WaitMode
0x14001841c  xor     edx, edx; WaitReason
0x14001841e  call    cs:__imp_KeWaitForSingleObject
0x140018425  nop     dword ptr [rax+rax+00h]
0x14001842a  mov     eax, [rbp+arg_20]
0x14001842d  mov     rcx, rdi; this
0x140018430  test    eax, eax
0x140018432  mov     [rdi+13Ch], eax
0x140018438  setnz   r15b
0x14001843c  mov     dl, r15b; bool
0x14001843f  call    ?ShouldCancelCommand@TpmTransport@@IEBA_N_N@Z; TpmTransport::ShouldCancelCommand(bool)
0x140018444  test    al, al
0x140018446  jz      short loc_140018499
0x140018448  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001844f  lea     r14, WPP_GLOBAL_Control
0x140018456  cmp     rcx, r14
0x140018459  jz      short loc_140018477
0x14001845b  mov     eax, [rcx+2Ch]
0x14001845e  test    al, 4
0x140018460  jz      short loc_140018477
0x140018462  mov     rcx, [rcx+18h]
0x140018466  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x14001846d  mov     edx, 0Eh
0x140018472  call    WPP_SF_
0x140018477  cmp     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x14001847e  mov     ebx, 80h
0x140018483  jnz     short loc_14001848F
0x140018485  mov     esi, 0C0291001h
0x14001848a  jmp     loc_14001884F
0x14001848f  mov     esi, 0C0000120h
0x140018494  jmp     loc_14001884F
0x140018499  lea     rsi, [rdi+140h]
0x1400184a0  mov     rcx, rsi
0x1400184a3  call    ?Read@?$TpmRegister@E@@QEAAEI@Z; TpmRegister<uchar>::Read(uint)
0x1400184a8  movzx   ebx, al
0x1400184ab  mov     byte ptr [rbp+arg_0], bl
0x1400184ae  cmp     bl, 0FFh
0x1400184b1  jz      loc_1400187E4
0x1400184b7  test    bl, bl
0x1400184b9  jns     loc_1400187E4
0x1400184bf  test    bl, 40h
0x1400184c2  jnz     loc_1400187E4
0x1400184c8  test    bl, 20h
0x1400184cb  jnz     short loc_14001850E
0x1400184cd  mov     r8b, 2
0x1400184d0  mov     rcx, rsi
0x1400184d3  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x1400184d8  mov     eax, [r13+0]
0x1400184dc  mov     r8, rsi
0x1400184df  mov     [rsp+60h+var_18], 1; char
0x1400184e4  mov     edx, 280h
0x1400184e9  mov     [rsp+60h+var_20], r14; __int64
0x1400184ee  mov     rcx, rdi; this
0x1400184f1  mov     [rsp+60h+var_28], r15b; char
0x1400184f6  mov     [rsp+60h+var_30], eax; int
0x1400184fa  mov     byte ptr [rsp+60h+Timeout], 20h ; ' '; char
0x1400184ff  call    ??$WaitForBitSet@E@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@E@@IE_NI1PEAE1@Z; TpmTransportTis::WaitForBitSet<uchar>(uint,TpmRegister<uchar> &,uint,uchar,bool,uint,bool,uchar *,bool)
0x140018504  mov     esi, eax
0x140018506  test    eax, eax
0x140018508  js      loc_14001884A
0x14001850e  mov     ebx, r14d
0x140018511  lea     r12, [rdi+144h]
0x140018518  lea     r14, WPP_GLOBAL_Control
0x14001851f  mov     r8b, 40h ; '@'
0x140018522  mov     rcx, r12
0x140018525  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x14001852a  mov     eax, [r13+4]
0x14001852e  mov     r8, r12
0x140018531  mov     [rsp+60h+var_18], 1; char
0x140018536  mov     edx, 28Eh
0x14001853b  mov     [rsp+60h+var_20], 0; __int64
0x140018544  mov     rcx, rdi; this
0x140018547  mov     [rsp+60h+var_28], r15b; char
0x14001854c  mov     [rsp+60h+var_30], eax; int
0x140018550  mov     byte ptr [rsp+60h+Timeout], 40h ; '@'; int
0x140018555  call    ??$WaitForBitSet@E@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@E@@IE_NI1PEAE1@Z; TpmTransportTis::WaitForBitSet<uchar>(uint,TpmRegister<uchar> &,uint,uchar,bool,uint,bool,uchar *,bool)
0x14001855a  xor     ecx, ecx
0x14001855c  mov     esi, eax
0x14001855e  test    eax, eax
0x140018560  jns     short loc_14001859C
0x140018562  test    ebx, ebx
0x140018564  jnz     short loc_140018590
0x140018566  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001856d  cmp     rcx, r14
0x140018570  jz      short loc_140018590
0x140018572  mov     eax, [rcx+2Ch]
0x140018575  test    al, 2
0x140018577  jz      short loc_140018590
0x140018579  mov     rcx, [rcx+18h]
0x14001857d  lea     edx, [rbx+10h]
0x140018580  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140018587  call    WPP_SF_
0x14001858c  inc     ebx
0x14001858e  jmp     short loc_14001851F
0x140018590  inc     ebx
0x140018592  cmp     ebx, 2
0x140018595  jb      short loc_14001851F
0x140018597  jmp     loc_14001884A
0x14001859c  cmp     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 6
0x1400185a3  jnz     short loc_1400185B6
0x1400185a5  lea     rcx, [rdi+150h]
0x1400185ac  xor     r8d, r8d
0x1400185af  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x1400185b4  xor     ecx, ecx
0x1400185b6  mov     rax, 0FFFFF78000000014h
0x1400185c0  mov     dword ptr [rdi+138h], 1
0x1400185ca  mov     word ptr [rbp+var_10], cx
0x1400185ce  mov     r12d, ecx
0x1400185d1  lea     rcx, [rdi+14Ch]
0x1400185d8  mov     rax, [rax]
0x1400185db  mov     [rbp+var_8], rax
0x1400185df  lea     rax, [rbp+var_10]
0x1400185e3  mov     r8, rcx
0x1400185e6  mov     [rsp+60h+var_20], rax; __int64
0x1400185eb  mov     edx, 2C4h
0x1400185f0  mov     eax, [r13+8]
0x1400185f4  mov     rcx, rdi; this
0x1400185f7  mov     [rsp+60h+var_28], r15b; char
0x1400185fc  mov     [rsp+60h+var_30], eax; int
0x140018600  call    ??$WaitForBitSet@G@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@G@@IG_NI1PEAG1@Z; TpmTransportTis::WaitForBitSet<ushort>(uint,TpmRegister<ushort> &,uint,ushort,bool,uint,bool,ushort *,bool)
0x140018605  xor     edx, edx
0x140018607  mov     esi, eax
0x140018609  test    eax, eax
0x14001860b  js      loc_14001884A
0x140018611  movzx   ebx, word ptr [rbp+var_10]
0x140018615  test    bx, bx
0x140018618  jz      short loc_140018658
0x14001861a  mov     esi, [rbp+arg_10]
0x14001861d  mov     r14, [rbp+arg_8]
0x140018621  dec     esi
0x140018623  cmp     r12d, esi
0x140018626  jnb     short loc_14001864A
0x140018628  mov     r8d, r12d
0x14001862b  lea     rcx, [rdi+148h]
0x140018632  mov     r8b, [r8+r14]
0x140018636  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x14001863b  mov     eax, 0FFFFh
0x140018640  xor     edx, edx
0x140018642  inc     r12d
0x140018645  add     bx, ax
0x140018648  jnz     short loc_140018623
0x14001864a  mov     word ptr [rbp+var_10], bx
0x14001864e  lea     r14, WPP_GLOBAL_Control
0x140018655  test    bx, bx
0x140018658  lea     rcx, [rdi+14Ch]
0x14001865f  jz      loc_1400185DF
0x140018665  mov     eax, [r13+8]
0x140018669  lea     r8, [rdi+144h]
0x140018670  mov     [rsp+60h+var_18], 1; char
0x140018675  mov     rcx, rdi; this
0x140018678  mov     [rsp+60h+var_20], rdx; __int64
0x14001867d  mov     edx, 2DEh
0x140018682  mov     [rsp+60h+var_28], r15b; char
0x140018687  mov     [rsp+60h+var_30], eax; int
0x14001868b  mov     byte ptr [rsp+60h+Timeout], 88h; char
0x140018690  call    ??$WaitForBitSet@E@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@E@@IE_NI1PEAE1@Z; TpmTransportTis::WaitForBitSet<uchar>(uint,TpmRegister<uchar> &,uint,uchar,bool,uint,bool,uchar *,bool)
0x140018695  mov     esi, eax
0x140018697  test    eax, eax
0x140018699  js      loc_14001884A
0x14001869f  mov     rax, [rbp+arg_8]
0x1400186a3  lea     rcx, [rdi+148h]
0x1400186aa  mov     r8d, r12d
0x1400186ad  mov     r8b, [r8+rax]
0x1400186b1  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x1400186b6  mov     [rsp+60h+var_18], 1; char
0x1400186bb  lea     rax, [rbp+arg_0]
0x1400186bf  mov     [rsp+60h+var_20], rax; __int64
0x1400186c4  mov     ebx, 80h
0x1400186c9  mov     eax, [r13+8]
0x1400186cd  mov     edx, 2EEh
0x1400186d2  mov     [rsp+60h+var_28], r15b; char
0x1400186d7  mov     rcx, rdi; this
0x1400186da  mov     [rsp+60h+var_30], eax; int
0x1400186de  lea     r15, [rdi+144h]
0x1400186e5  mov     r8, r15
0x1400186e8  mov     byte ptr [rsp+60h+Timeout], bl; char
0x1400186ec  call    ??$WaitForBitSet@E@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@E@@IE_NI1PEAE1@Z; TpmTransportTis::WaitForBitSet<uchar>(uint,TpmRegister<uchar> &,uint,uchar,bool,uint,bool,uchar *,bool)
0x1400186f1  xor     r9d, r9d
0x1400186f4  mov     esi, eax
0x1400186f6  test    eax, eax
0x1400186f8  js      loc_14001884F
0x1400186fe  mov     r12, 0FFFFF78000000014h
0x140018708  mov     r8, [r12]
0x14001870c  mov     eax, cs:dword_1400470A0
0x140018712  cmp     eax, 5
0x140018715  jbe     short loc_14001875B
0x140018717  call    _tlgKeywordOn
0x14001871c  test    al, al
0x14001871e  jz      short loc_14001875B
0x140018720  sub     r8, [rbp+var_8]
0x140018724  lea     rax, [rbp+arg_8]
0x140018728  mov     qword ptr [rsp+60h+var_30], rax
0x14001872d  lea     rdx, byte_140041CAF
0x140018734  lea     rax, [rbp+arg_10]
0x140018738  mov     [rbp+arg_8], r8
0x14001873c  mov     [rsp+60h+var_38], rax
0x140018741  lea     rax, [rbp+var_8]
0x140018745  mov     [rsp+60h+Timeout], rax
0x14001874a  mov     [rbp+arg_10], r9d
0x14001874e  mov     [rbp+var_8], 1000000h
0x140018756  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14001875b  test    byte ptr [rbp+arg_0], 8
0x14001875f  jz      short loc_1400187BE
0x140018761  test    cs:TPMEnableBits, 1
0x140018768  jz      short loc_14001878C
0x14001876a  movzx   eax, byte ptr [rbp+arg_0]
0x14001876e  lea     rdx, TPM_HW_STATE_ERROR
0x140018775  mov     dword ptr [rsp+60h+var_38], eax
0x140018779  mov     r9d, 2Ch ; ','
0x14001877f  mov     dword ptr [rsp+60h+Timeout], 305h
0x140018787  call    McTemplateK0dqq_EtwWriteTransfer
0x14001878c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018793  cmp     rcx, r14
0x140018796  jz      short loc_1400187B4
0x140018798  mov     eax, [rcx+2Ch]
0x14001879b  test    al, 1
0x14001879d  jz      short loc_1400187B4
0x14001879f  mov     rcx, [rcx+18h]
0x1400187a3  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x1400187aa  mov     edx, 11h
0x1400187af  call    WPP_SF_
0x1400187b4  mov     esi, 0C0000184h
0x1400187b9  jmp     loc_14001884F
0x1400187be  mov     r8b, 20h ; ' '
0x1400187c1  mov     rcx, r15
0x1400187c4  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x1400187c9  mov     rax, [r12]
0x1400187cd  mov     ecx, [r13+10h]
0x1400187d1  imul    rdx, rcx, 2710h
0x1400187d8  add     rdx, rax
0x1400187db  mov     [rdi+160h], rdx
0x1400187e2  jmp     short loc_14001884F
0x1400187e4  test    cs:TPMEnableBits, 1
0x1400187eb  jz      short loc_14001880B
0x1400187ed  mov     dword ptr [rsp+60h+var_38], ebx
0x1400187f1  lea     rdx, TPM_HW_STATE_ERROR
0x1400187f8  mov     r9d, 2Ch ; ','
0x1400187fe  mov     dword ptr [rsp+60h+Timeout], 26Eh
0x140018806  call    McTemplateK0dqq_EtwWriteTransfer
0x14001880b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018812  lea     r14, WPP_GLOBAL_Control
0x140018819  cmp     rcx, r14
0x14001881c  jz      short loc_140018845
0x14001881e  mov     eax, [rcx+2Ch]
0x140018821  test    al, 1
0x140018823  jz      short loc_140018845
0x140018825  mov     r9d, [rdi+140h]
0x14001882c  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140018833  mov     rcx, [rcx+18h]
0x140018837  mov     edx, 0Fh
0x14001883c  mov     dword ptr [rsp+60h+Timeout], ebx
0x140018840  call    WPP_SF_Dd
0x140018845  mov     esi, 0C0000184h
0x14001884a  mov     ebx, 80h
0x14001884f  lea     rcx, [rdi+rbx]; Mutex
0x140018853  xor     edx, edx; Wait
0x140018855  call    cs:__imp_KeReleaseMutex
0x14001885c  nop     dword ptr [rax+rax+00h]
0x140018861  mov     rbx, [rsp+60h+arg_18]
0x140018869  mov     eax, esi
0x14001886b  add     rsp, 60h
0x14001886f  pop     r15
0x140018871  pop     r14
0x140018873  pop     r13
0x140018875  pop     r12
0x140018877  pop     rdi
0x140018878  pop     rsi
0x140018879  pop     rbp
0x14001887a  retn
```
