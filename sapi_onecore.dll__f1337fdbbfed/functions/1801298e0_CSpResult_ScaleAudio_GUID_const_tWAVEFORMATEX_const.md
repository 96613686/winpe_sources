# CSpResult::ScaleAudio(_GUID const *,tWAVEFORMATEX const *)

- ea: `0x1801298e0`
- end: `0x180129c75`
- name: `?ScaleAudio@CSpResult@@UEAAJPEBU_GUID@@PEBUtWAVEFORMATEX@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(CSpResult *__hidden this, const struct _GUID *, const struct tWAVEFORMATEX *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180117830`

## callees

- `0x180038fac`
- `0x18003a84c`
- `0x1800651fc`
- `0x18007642c`
- `0x18007a2dc`
- `0x18007d7b1`
- `0x1800cada8`
- `0x1800cae10`
- `0x180112734`
- `0x180128d38`
- `0x18012929c`
- `0x1801298e0`
- `0x180129f00`
- `0x18017e0f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180129920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180129920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129964`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129c4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129964`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012995a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012995a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c45`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpResult::ScaleAudio(CSpResult *this, const struct _GUID *a2, const struct tWAVEFORMATEX *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  const unsigned __int8 *v8; // rax
  int DesiredFormatAudioData; // ebx
  struct tWAVEFORMATEX *v10; // rsi
  unsigned __int64 v11; // rcx
  unsigned int v12; // r12d
  int v13; // edx
  unsigned __int64 v14; // r8
  double v15; // xmm1_8
  __int64 v16; // rdx
  double v17; // xmm0_8
  struct SPRESULTHEADER *v18; // r12
  unsigned int v19; // eax
  __int64 v20; // r14
  unsigned int v21; // [rsp+20h] [rbp-B9h]
  unsigned int v22; // [rsp+40h] [rbp-99h]
  unsigned int Size; // [rsp+50h] [rbp-89h] BYREF
  unsigned int Size_4; // [rsp+54h] [rbp-85h] BYREF
  void *Src; // [rsp+58h] [rbp-81h] BYREF
  GUID v26; // [rsp+60h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-69h]
  int v28; // [rsp+78h] [rbp-61h]
  struct _GUID v29; // [rsp+80h] [rbp-59h] BYREF
  struct tWAVEFORMATEX *v30; // [rsp+90h] [rbp-49h]
  int v31; // [rsp+98h] [rbp-41h]
  GUID v32; // [rsp+A0h] [rbp-39h] BYREF
  LPVOID v33; // [rsp+B0h] [rbp-29h]
  int v34; // [rsp+B8h] [rbp-21h]
  struct SPRESULTHEADER *v35[2]; // [rsp+C0h] [rbp-19h] BYREF
  unsigned __int8 *v36[2]; // [rsp+D0h] [rbp-9h]
  __int128 v37; // [rsp+E0h] [rbp+7h]
  __int64 v38; // [rsp+F0h] [rbp+17h]
  __int64 v39; // [rsp+F8h] [rbp+1Fh]

  v39 = ((unsigned __int64)this + 24) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  v6 = (struct _RTL_CRITICAL_SECTION *)(v39 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v39 + 8));
  v26 = GUID_NULL;
  pv = 0;
  v28 = 0;
  if ( (int)CSpStreamFormat::ParamValidateAssignFormat((CSpStreamFormat *)&v26, a2, a3, 1) >= 0 )
  {
    v8 = (const unsigned __int8 *)*((_QWORD *)this + 10);
    if ( *((_DWORD *)v8 + 16) && *((_DWORD *)v8 + 22) && *((_DWORD *)v8 + 21) )
    {
      Size_4 = 0;
      v29 = GUID_NULL;
      v30 = 0;
      v31 = 0;
      DesiredFormatAudioData = CSpStreamFormat::Deserialize(
                                 (CSpStreamFormat *)&v29,
                                 &v8[*((unsigned int *)v8 + 22)],
                                 &Size_4);
      if ( DesiredFormatAudioData >= 0
        && (int)CSpStreamFormat::ParamValidateAssignFormat((CSpStreamFormat *)&v26, &v29, v30, 1) < 0 )
      {
        DesiredFormatAudioData = -2147201021;
      }
      v10 = v30;
      if ( *((_DWORD *)this + 46) )
      {
        DesiredFormatAudioData = -2147200930;
      }
      else if ( DesiredFormatAudioData >= 0 )
      {
        v11 = *(_QWORD *)&v30->wFormatTag - *(_QWORD *)&a3->wFormatTag;
        if ( *(_QWORD *)&v30->wFormatTag == *(_QWORD *)&a3->wFormatTag )
        {
          v11 = *(_QWORD *)&v30->nAvgBytesPerSec - *(_QWORD *)&a3->nAvgBytesPerSec;
          if ( !v11 )
            v11 = v30->cbSize - (unsigned __int64)a3->cbSize;
        }
        if ( v11 )
        {
          Src = 0;
          Size = 0;
          v12 = Size_4;
          DesiredFormatAudioData = SpGetDesiredFormatAudioData(
                                     *(_DWORD *)(*((_QWORD *)this + 10) + 84LL),
                                     (const unsigned __int8 *)(*((_QWORD *)this + 10)
                                                             + *(unsigned int *)(*((_QWORD *)this + 10) + 88LL)),
                                     *(_DWORD *)(*((_QWORD *)this + 10) + 84LL) - Size_4,
                                     a2,
                                     a3,
                                     (unsigned __int8 **)&Src,
                                     &Size);
          *(_OWORD *)v35 = 0;
          *(_OWORD *)v36 = 0;
          v37 = 0;
          v38 = 0;
          if ( DesiredFormatAudioData >= 0 )
          {
            v13 = Size;
            v14 = a3->cbSize + Size + v12 - (unsigned __int64)v10->cbSize;
            if ( v14 < 0xFFFFFFFF )
            {
              DesiredFormatAudioData = CResultHeader::InitFromHeader(
                                         (CResultHeader *)v35,
                                         *((struct SPRESULTHEADER **)this + 10),
                                         4u,
                                         0,
                                         v21,
                                         v14,
                                         0,
                                         0,
                                         v22);
              v13 = Size;
            }
            else
            {
              DesiredFormatAudioData = -2147024882;
            }
            v15 = (double)v13;
            v16 = *(_QWORD *)(*((_QWORD *)this + 10) + 56LL) - *(_QWORD *)(*((_QWORD *)this + 10) + 48LL);
            if ( v16 < 0 )
              v17 = (double)(int)(v16 & 1 | ((unsigned __int64)v16 >> 1))
                  + (double)(int)(v16 & 1 | ((unsigned __int64)v16 >> 1));
            else
              v17 = (double)(int)v16;
            *((float *)this + 68) = v15 / v17;
            v32 = GUID_NULL;
            v33 = 0;
            v34 = 0;
            v18 = v35[0];
            if ( DesiredFormatAudioData >= 0 )
            {
              DesiredFormatAudioData = CSpStreamFormat::AssignFormat((CSpStreamFormat *)&v32, a2, a3);
              if ( DesiredFormatAudioData >= 0 )
              {
                v19 = CSpStreamFormat::SerializeSize((CSpStreamFormat *)&v32);
                v20 = v19;
                if ( v19 + Size <= *((_DWORD *)v18 + 21) )
                {
                  CSpStreamFormat::Serialize((CSpStreamFormat *)&v32, v36[1], v19);
                  memcpy_0(&v36[1][v20], Src, Size);
                }
                else
                {
                  DesiredFormatAudioData = -2147418113;
                }
              }
            }
            CoTaskMemFree(v33);
            if ( DesiredFormatAudioData >= 0 )
            {
              *((_BYTE *)this + 116) = 1;
              CSpResult::InternalScalePhrase(this, v18);
              CoTaskMemFree(*((LPVOID *)this + 10));
              *((_QWORD *)this + 10) = 0;
              v35[0] = 0;
              CResultHeader::Clear((CResultHeader *)v35);
              DesiredFormatAudioData = CSpResult::InitResult(this, 0, v18, 0, SPEI_UNDEFINED, 0);
            }
          }
          operator delete(Src);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v35);
        }
      }
      CoTaskMemFree(v10);
      CoTaskMemFree(pv);
      LeaveCriticalSection(v6);
      return (unsigned int)DesiredFormatAudioData;
    }
    else
    {
      CoTaskMemFree(pv);
      LeaveCriticalSection(v6);
      return 2147766320LL;
    }
  }
  else
  {
    CoTaskMemFree(pv);
    LeaveCriticalSection(v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1801298e0  mov     [rsp-8+arg_18], rbx
0x1801298e5  push    rbp
0x1801298e6  push    rsi
0x1801298e7  push    rdi
0x1801298e8  push    r12
0x1801298ea  push    r13
0x1801298ec  push    r14
0x1801298ee  push    r15
0x1801298f0  lea     rbp, [rsp-27h]
0x1801298f5  sub     rsp, 100h
0x1801298fc  mov     r14, r8
0x1801298ff  mov     r13, rdx
0x180129902  mov     rdi, rcx
0x180129905  mov     rax, rcx
0x180129908  add     rcx, 18h
0x18012990c  neg     rax
0x18012990f  sbb     rdx, rdx
0x180129912  and     rdx, rcx
0x180129915  mov     [rbp+57h+var_38], rdx
0x180129919  lea     r15, [rdx+8]
0x18012991d  mov     rcx, r15; lpCriticalSection
0x180129920  call    cs:__imp_EnterCriticalSection
0x180129926  nop
0x180129927  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18012992e  movdqu  [rbp+57h+var_D0], xmm0
0x180129933  xor     r12d, r12d
0x180129936  mov     [rbp+57h+pv], r12
0x18012993a  mov     [rbp+57h+var_B8], r12d
0x18012993e  lea     r9d, [r12+1]; int
0x180129943  mov     r8, r14; struct tWAVEFORMATEX *
0x180129946  mov     rdx, r13; struct _GUID *
0x180129949  lea     rcx, [rbp+57h+var_D0]; this
0x18012994d  call    ?ParamValidateAssignFormat@CSpStreamFormat@@QEAAJAEBU_GUID@@PEBUtWAVEFORMATEX@@H@Z; CSpStreamFormat::ParamValidateAssignFormat(_GUID const &,tWAVEFORMATEX const *,int)
0x180129952  test    eax, eax
0x180129954  jns     short loc_180129974
0x180129956  mov     rcx, [rbp+57h+pv]; pv
0x18012995a  call    cs:__imp_CoTaskMemFree
0x180129960  nop
0x180129961  mov     rcx, r15; lpCriticalSection
0x180129964  call    cs:__imp_LeaveCriticalSection
0x18012996a  mov     eax, 80070057h
0x18012996f  jmp     loc_180129C5A
0x180129974  mov     rax, [rdi+50h]
0x180129978  cmp     [rax+40h], r12d
0x18012997c  jz      loc_180129C41
0x180129982  cmp     [rax+58h], r12d
0x180129986  jz      loc_180129C41
0x18012998c  cmp     [rax+54h], r12d
0x180129990  jz      loc_180129C41
0x180129996  mov     dword ptr [rsp+130h+Size+4], r12d
0x18012999b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801299a2  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1801299a7  mov     [rbp+57h+var_A0], r12
0x1801299ab  mov     [rbp+57h+var_98], r12d
0x1801299af  mov     edx, [rax+58h]
0x1801299b2  add     rdx, rax; unsigned __int8 *
0x1801299b5  lea     r8, [rsp+130h+Size+4]; unsigned int *
0x1801299ba  lea     rcx, [rbp+57h+var_B0]; this
0x1801299be  call    ?Deserialize@CSpStreamFormat@@QEAAJPEBEPEAK@Z; CSpStreamFormat::Deserialize(uchar const *,ulong *)
0x1801299c3  mov     ebx, eax
0x1801299c5  test    eax, eax
0x1801299c7  js      short loc_1801299EA
0x1801299c9  mov     r9d, 1; int
0x1801299cf  mov     r8, [rbp+57h+var_A0]; struct tWAVEFORMATEX *
0x1801299d3  lea     rdx, [rbp+57h+var_B0]; struct _GUID *
0x1801299d7  lea     rcx, [rbp+57h+var_D0]; this
0x1801299db  call    ?ParamValidateAssignFormat@CSpStreamFormat@@QEAAJAEBU_GUID@@PEBUtWAVEFORMATEX@@H@Z; CSpStreamFormat::ParamValidateAssignFormat(_GUID const &,tWAVEFORMATEX const *,int)
0x1801299e0  mov     ecx, 80045003h
0x1801299e5  test    eax, eax
0x1801299e7  cmovs   ebx, ecx
0x1801299ea  mov     rsi, [rbp+57h+var_A0]
0x1801299ee  cmp     [rdi+0B8h], r12d
0x1801299f5  jz      short loc_180129A01
0x1801299f7  mov     ebx, 8004505Eh
0x1801299fc  jmp     loc_180129C1F
0x180129a01  test    ebx, ebx
0x180129a03  js      loc_180129C1F
0x180129a09  mov     rcx, [rsi]
0x180129a0c  sub     rcx, [r14]
0x180129a0f  jnz     short loc_180129A27
0x180129a11  mov     rcx, [rsi+8]
0x180129a15  sub     rcx, [r14+8]
0x180129a19  jnz     short loc_180129A27
0x180129a1b  movzx   ecx, word ptr [rsi+10h]
0x180129a1f  movzx   eax, word ptr [r14+10h]
0x180129a24  sub     rcx, rax
0x180129a27  test    rcx, rcx
0x180129a2a  jz      loc_180129C1F
0x180129a30  mov     [rsp+130h+Src], r12
0x180129a35  mov     dword ptr [rsp+130h+Size], r12d
0x180129a3a  mov     rax, [rdi+50h]
0x180129a3e  mov     ecx, [rax+54h]; unsigned int
0x180129a41  mov     r8d, ecx
0x180129a44  mov     r12d, dword ptr [rsp+130h+Size+4]
0x180129a49  sub     r8d, r12d; unsigned int
0x180129a4c  mov     edx, [rax+58h]
0x180129a4f  add     rdx, rax; unsigned __int8 *
0x180129a52  lea     rax, [rsp+130h+Size]
0x180129a57  mov     [rsp+130h+var_100], rax; unsigned int *
0x180129a5c  lea     rax, [rsp+130h+Src]
0x180129a61  mov     [rsp+130h+var_108], rax; unsigned __int8 **
0x180129a66  mov     qword ptr [rsp+130h+var_110], r14; unsigned int
0x180129a6b  mov     r9, r13; struct _GUID *
0x180129a6e  call    ?SpGetDesiredFormatAudioData@@YAJKPEBEKPEBU_GUID@@PEBUtWAVEFORMATEX@@PEAPEAEPEAK@Z; SpGetDesiredFormatAudioData(ulong,uchar const *,ulong,_GUID const *,tWAVEFORMATEX const *,uchar * *,ulong *)
0x180129a73  mov     ebx, eax
0x180129a75  xorps   xmm0, xmm0
0x180129a78  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180129a7d  xorps   xmm1, xmm1
0x180129a80  movdqu  xmmword ptr [rbp+57h+var_60], xmm1
0x180129a85  movdqu  [rbp+57h+var_50], xmm0
0x180129a8a  xor     r9d, r9d
0x180129a8d  mov     [rbp+57h+var_40], r9
0x180129a91  test    eax, eax
0x180129a93  js      loc_180129C0A
0x180129a99  mov     edx, dword ptr [rsp+130h+Size]
0x180129a9d  lea     r8d, [rdx+r12]
0x180129aa1  movzx   eax, word ptr [rsi+10h]
0x180129aa5  sub     r8, rax
0x180129aa8  movzx   eax, word ptr [r14+10h]
0x180129aad  add     r8, rax
0x180129ab0  mov     eax, 0FFFFFFFFh
0x180129ab5  cmp     r8, rax
0x180129ab8  jb      short loc_180129AC1
0x180129aba  mov     ebx, 8007000Eh
0x180129abf  jmp     short loc_180129AED
0x180129ac1  mov     [rsp+130h+var_F8], r9d; unsigned int
0x180129ac6  mov     dword ptr [rsp+130h+var_100], r9d; unsigned int
0x180129acb  mov     dword ptr [rsp+130h+var_108], r8d; unsigned int
0x180129ad0  xor     r9d, r9d; unsigned int
0x180129ad3  lea     r8d, [r9+4]; unsigned int
0x180129ad7  mov     rdx, [rdi+50h]; struct SPRESULTHEADER *
0x180129adb  lea     rcx, [rbp+57h+var_70]; this
0x180129adf  call    ?InitFromHeader@CResultHeader@@QEAAJPEAUSPRESULTHEADER@@KKKKKKK@Z; CResultHeader::InitFromHeader(SPRESULTHEADER *,ulong,ulong,ulong,ulong,ulong,ulong,ulong)
0x180129ae4  mov     ebx, eax
0x180129ae6  mov     edx, dword ptr [rsp+130h+Size]
0x180129aea  xor     r9d, r9d
0x180129aed  mov     rcx, [rdi+50h]
0x180129af1  mov     eax, edx
0x180129af3  xorps   xmm1, xmm1
0x180129af6  cvtsi2sd xmm1, rax
0x180129afb  mov     rdx, [rcx+38h]
0x180129aff  sub     rdx, [rcx+30h]
0x180129b03  xorps   xmm0, xmm0
0x180129b06  js      short loc_180129B0F
0x180129b08  cvtsi2sd xmm0, rdx
0x180129b0d  jmp     short loc_180129B24
0x180129b0f  mov     rax, rdx
0x180129b12  shr     rax, 1
0x180129b15  and     edx, 1
0x180129b18  or      rax, rdx
0x180129b1b  cvtsi2sd xmm0, rax
0x180129b20  addsd   xmm0, xmm0
0x180129b24  divsd   xmm1, xmm0
0x180129b28  cvtpd2ps xmm0, xmm1
0x180129b2c  movss   dword ptr [rdi+110h], xmm0
0x180129b34  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180129b3b  movdqu  [rbp+57h+var_90], xmm1
0x180129b40  mov     [rbp+57h+var_80], r9
0x180129b44  mov     [rbp+57h+var_78], r9d
0x180129b48  mov     r12, [rbp+57h+var_70]
0x180129b4c  test    ebx, ebx
0x180129b4e  js      short loc_180129BAB
0x180129b50  mov     r8, r14; struct tWAVEFORMATEX *
0x180129b53  mov     rdx, r13; struct _GUID *
0x180129b56  lea     rcx, [rbp+57h+var_90]; this
0x180129b5a  call    ?AssignFormat@CSpStreamFormat@@QEAAJAEBU_GUID@@PEBUtWAVEFORMATEX@@@Z; CSpStreamFormat::AssignFormat(_GUID const &,tWAVEFORMATEX const *)
0x180129b5f  mov     ebx, eax
0x180129b61  test    eax, eax
0x180129b63  js      short loc_180129BAB
0x180129b65  lea     rcx, [rbp+57h+var_90]; this
0x180129b69  call    ?SerializeSize@CSpStreamFormat@@QEBAKXZ; CSpStreamFormat::SerializeSize(void)
0x180129b6e  mov     r14d, eax
0x180129b71  mov     edx, dword ptr [rsp+130h+Size]
0x180129b75  add     edx, eax
0x180129b77  cmp     edx, [r12+54h]
0x180129b7c  jbe     short loc_180129B85
0x180129b7e  mov     ebx, 8000FFFFh
0x180129b83  jmp     short loc_180129BAB
0x180129b85  mov     r8d, r14d; unsigned int
0x180129b88  mov     rdx, [rbp+57h+var_60+8]; unsigned __int8 *
0x180129b8c  lea     rcx, [rbp+57h+var_90]; this
0x180129b90  call    ?Serialize@CSpStreamFormat@@QEBAKPEAEK@Z; CSpStreamFormat::Serialize(uchar *,ulong)
0x180129b95  mov     r8d, dword ptr [rsp+130h+Size]; Size
0x180129b9a  mov     rcx, r14
0x180129b9d  add     rcx, [rbp+57h+var_60+8]; void *
0x180129ba1  mov     rdx, [rsp+130h+Src]; Src
0x180129ba6  call    memcpy_0
0x180129bab  mov     rcx, [rbp+57h+var_80]; pv
0x180129baf  call    cs:__imp_CoTaskMemFree
0x180129bb5  test    ebx, ebx
0x180129bb7  js      short loc_180129C0A
0x180129bb9  mov     byte ptr [rdi+74h], 1
0x180129bbd  mov     rdx, r12; struct SPRESULTHEADER *
0x180129bc0  mov     rcx, rdi; this
0x180129bc3  call    ?InternalScalePhrase@CSpResult@@AEAAJPEAUSPRESULTHEADER@@@Z; CSpResult::InternalScalePhrase(SPRESULTHEADER *)
0x180129bc8  mov     rcx, [rdi+50h]; pv
0x180129bcc  call    cs:__imp_CoTaskMemFree
0x180129bd2  mov     qword ptr [rdi+50h], 0
0x180129bda  mov     [rbp+57h+var_70], 0
0x180129be2  lea     rcx, [rbp+57h+var_70]; this
0x180129be6  call    ?Clear@CResultHeader@@QEAAXXZ; CResultHeader::Clear(void)
0x180129beb  mov     byte ptr [rsp+130h+var_108], 0; bool
0x180129bf0  mov     [rsp+130h+var_110], 0; enum SPEVENTENUM
0x180129bf8  xor     r9d, r9d; bool
0x180129bfb  mov     r8, r12; struct SPRESULTHEADER *
0x180129bfe  xor     edx, edx; struct CRecoCtxt *
0x180129c00  mov     rcx, rdi; this
0x180129c03  call    ?InitResult@CSpResult@@QEAAJPEAVCRecoCtxt@@PEAUSPRESULTHEADER@@_NW4SPEVENTENUM@@2@Z; CSpResult::InitResult(CRecoCtxt *,SPRESULTHEADER *,bool,SPEVENTENUM,bool)
0x180129c08  mov     ebx, eax
0x180129c0a  mov     rcx, [rsp+130h+Src]; Block
0x180129c0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180129c14  nop
0x180129c15  lea     rcx, [rbp+57h+var_70]
0x180129c19  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180129c1e  nop
0x180129c1f  mov     rcx, rsi; pv
0x180129c22  call    cs:__imp_CoTaskMemFree
0x180129c28  nop
0x180129c29  mov     rcx, [rbp+57h+pv]; pv
0x180129c2d  call    cs:__imp_CoTaskMemFree
0x180129c33  nop
0x180129c34  mov     rcx, r15; lpCriticalSection
0x180129c37  call    cs:__imp_LeaveCriticalSection
0x180129c3d  mov     eax, ebx
0x180129c3f  jmp     short loc_180129C5A
0x180129c41  mov     rcx, [rbp+57h+pv]; pv
0x180129c45  call    cs:__imp_CoTaskMemFree
0x180129c4b  nop
0x180129c4c  mov     rcx, r15; lpCriticalSection
0x180129c4f  call    cs:__imp_LeaveCriticalSection
0x180129c55  mov     eax, 80045030h
0x180129c5a  mov     rbx, [rsp+130h+arg_18]
0x180129c62  add     rsp, 100h
0x180129c69  pop     r15
0x180129c6b  pop     r14
0x180129c6d  pop     r13
0x180129c6f  pop     r12
0x180129c71  pop     rdi
0x180129c72  pop     rsi
0x180129c73  pop     rbp
0x180129c74  retn
```
