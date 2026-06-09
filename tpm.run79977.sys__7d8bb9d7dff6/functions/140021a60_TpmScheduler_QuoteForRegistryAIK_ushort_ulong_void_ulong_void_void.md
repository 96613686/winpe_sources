# TpmScheduler::_QuoteForRegistryAIK(ushort *,ulong,void *,ulong,void *,void *)

- ea: `0x140021a60`
- end: `0x140021fd8`
- name: `?_QuoteForRegistryAIK@TpmScheduler@@CAJPEAGKPEAXK11@Z`
- size: `1400`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x140007a94`
- `0x14000c22c`
- `0x14000e4e4`
- `0x14001a41c`
- `0x1400210ec`
- `0x14002114c`
- `0x140021410`
- `0x140021a60`
- `0x140022050`
- `0x140039740`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall TpmScheduler::_QuoteForRegistryAIK(
        unsigned __int16 *a1,
        int a2,
        _DWORD *a3,
        unsigned int a4,
        TpmDevice ***a5)
{
  struct TpmContext *v5; // r14
  TpmDevice **v6; // r13
  BufferAccessor *v10; // rsi
  size_t v11; // rdx
  NTSTATUS v12; // ebx
  unsigned int v13; // r9d
  __int64 v14; // rcx
  unsigned __int64 v15; // r12
  char *v16; // rdi
  __int64 v17; // r10
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // ecx
  int Context; // eax
  unsigned int v24; // r9d
  unsigned int v25; // r12d
  unsigned int v26; // edi
  unsigned int v27; // r15d
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  unsigned int cbOutput; // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+40h] [rbp-C0h]
  struct TpmContext *v32; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v33; // [rsp+78h] [rbp-88h]
  unsigned int v34; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v35; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v36; // [rsp+8Ch] [rbp-74h] BYREF
  size_t pcbLength; // [rsp+90h] [rbp-70h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+98h] [rbp-68h]
  unsigned __int8 v39[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+B0h] [rbp-50h]
  unsigned __int8 v42[4]; // [rsp+B8h] [rbp-48h] BYREF
  char v43; // [rsp+BCh] [rbp-44h]
  unsigned __int8 v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v45; // [rsp+D0h] [rbp-30h]
  UCHAR pbOutput[16]; // [rsp+D8h] [rbp-28h] BYREF
  int v47; // [rsp+E8h] [rbp-18h]
  unsigned __int8 v48[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 v49[256]; // [rsp+1F0h] [rbp+F0h] BYREF

  psz = a1;
  v34 = a4;
  v5 = 0;
  v32 = 0;
  v6 = *a5;
  v33 = 0;
  v40 = 0;
  v41 = 0;
  v43 = 0;
  v45 = 0;
  v47 = 0;
  *(_OWORD *)v44 = 0;
  *(_DWORD *)v42 = -142671104;
  *(_OWORD *)pbOutput = 0;
  memset(v48, 0, sizeof(v48));
  v36 = 256;
  memset(v49, 0, sizeof(v49));
  v35 = 256;
  v10 = (BufferAccessor *)a5[1];
  pcbLength = 0;
  v12 = RtlStringCbLengthW(psz, v11, &pcbLength);
  if ( a2 == 3 && a4 >= 0x14 )
  {
    *(_QWORD *)v39 = MEMORY[0xFFFFF78000000014];
    if ( a3 )
    {
      if ( *a3 == 1297105744 )
      {
        v14 = (unsigned int)a3[1];
        if ( (unsigned int)v14 >= 0x14 && a3[2] == 1 && (a3[3] & 1) == 0 )
        {
          v15 = (unsigned int)a3[4];
          if ( v34 >= (int)v15 + (int)v14 && v15 >= 0x17 )
          {
            v16 = (char *)a3 + v14;
            v17 = ((*((unsigned __int8 *)a3 + v14 + 21)
                  + ((*((unsigned __int8 *)a3 + v14 + 20) + (*((unsigned __int8 *)a3 + v14 + 19) << 8)) << 8)) << 8)
                + (unsigned int)*((unsigned __int8 *)a3 + v14 + 22)
                + 23;
            if ( v15 >= v17 + 4 )
            {
              v18 = (unsigned __int8)v16[(unsigned int)(v17 + 3)]
                  + (unsigned int)v17
                  + (((unsigned __int8)v16[(unsigned int)(v17 + 2)]
                    + ((((unsigned __int8)v16[v17] << 8) + (unsigned __int8)v16[(unsigned int)(v17 + 1)]) << 8)) << 8)
                  + 4;
              if ( v15 >= v18 + 4 )
              {
                v19 = (unsigned int)(v18 + 3);
                v20 = ((unsigned __int8)v16[(unsigned int)(v18 + 2)]
                     + ((((unsigned __int8)v16[v18] << 8) + (unsigned __int8)v16[(unsigned int)(v18 + 1)]) << 8)) << 8;
                v21 = v18 + 4;
                v22 = v20 + (unsigned __int8)v16[v19];
                if ( (unsigned int)v15 >= v22 + v21
                  && !(unsigned int)BCryptHashData(L"SHA1", 0, 0, (unsigned __int8 *)&v16[v21], v22, pbOutput, 0x14u) )
                {
                  Context = TpmDevice::CreateContext(v6[2], (void **)&v32);
                  v5 = v32;
                  v12 = Context;
                  if ( Context >= 0 )
                  {
                    if ( v16 )
                    {
                      v12 = TpmScheduler::ExecuteInternalCmd(
                              (TpmScheduler *)v6,
                              v32,
                              0xC2u,
                              0x41u,
                              v44,
                              0x14u,
                              0,
                              0,
                              "u32Au8hpu32");
                      if ( v12 >= 0 )
                      {
                        v12 = TpmScheduler::Quote2(
                                (TpmScheduler *)v6,
                                v5,
                                v33,
                                v44,
                                v29,
                                v39,
                                cbOutput,
                                v42,
                                v31,
                                0,
                                v48,
                                &v36,
                                v49,
                                &v35);
                        TpmScheduler::FlushSpecific((TpmScheduler *)v6, v5, v33, v24);
                        v33 = 0;
                        if ( v12 < 0 )
                          goto LABEL_37;
                        TpmDevice::DeleteContext(v6[2], v5);
                        v5 = 0;
                        LODWORD(v32) = -1073676284;
                        v12 = BufferAccessor::Append(v10, &v32, 4u);
                        if ( v12 >= 0 )
                        {
                          v25 = v34;
                          v26 = v36;
                          v27 = v35;
                          v32 = (struct TpmContext *)(v36 + 22LL + v35 + (unsigned __int64)(v34 + 32));
                          v12 = BufferAccessor::Append(v10, &v32, 8u);
                          if ( v12 >= 0 )
                          {
                            LODWORD(v32) = -2146959357;
                            v12 = BufferAccessor::Append(v10, &v32, 4u);
                            if ( v12 >= 0 )
                            {
                              LODWORD(v32) = v25 + 2;
                              v12 = BufferAccessor::Append(v10, &v32, 4u);
                              if ( v12 >= 0 )
                              {
                                v12 = BufferAccessor::Append(v10, psz, pcbLength);
                                if ( v12 >= 0 )
                                {
                                  LOWORD(v34) = 0;
                                  v12 = BufferAccessor::Append(v10, &v34, 2u);
                                  if ( v12 >= 0 )
                                  {
                                    LODWORD(v32) = -2146959356;
                                    v12 = BufferAccessor::Append(v10, &v32, 4u);
                                    if ( v12 >= 0 )
                                    {
                                      LODWORD(v32) = 20;
                                      v12 = BufferAccessor::Append(v10, &v32, 4u);
                                      if ( v12 >= 0 )
                                      {
                                        v12 = BufferAccessor::Append(v10, pbOutput, 0x14u);
                                        if ( v12 >= 0 )
                                        {
                                          LODWORD(v32) = -2146959359;
                                          v12 = BufferAccessor::Append(v10, &v32, 4u);
                                          if ( v12 >= 0 )
                                          {
                                            LODWORD(v32) = v26;
                                            v12 = BufferAccessor::Append(v10, &v32, 4u);
                                            if ( v12 >= 0 )
                                            {
                                              v12 = BufferAccessor::Append(v10, v48, v26);
                                              if ( v12 >= 0 )
                                              {
                                                LODWORD(v32) = -2146959358;
                                                v12 = BufferAccessor::Append(v10, &v32, 4u);
                                                if ( v12 >= 0 )
                                                {
                                                  LODWORD(v32) = v27;
                                                  v12 = BufferAccessor::Append(v10, &v32, 4u);
                                                  if ( v12 >= 0 )
                                                    v12 = BufferAccessor::Append(v10, v49, v27);
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                    else
                    {
                      v12 = -1073741811;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v33 )
  {
    if ( !v5 )
      return (unsigned int)v12;
    TpmScheduler::FlushSpecific((TpmScheduler *)v6, v5, v33, v13);
  }
LABEL_37:
  if ( v5 )
    TpmDevice::DeleteContext(v6[2], v5);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140021a60  mov     [rsp-8+arg_8], rbx
0x140021a65  push    rbp
0x140021a66  push    rsi
0x140021a67  push    rdi
0x140021a68  push    r12
0x140021a6a  push    r13
0x140021a6c  push    r14
0x140021a6e  push    r15
0x140021a70  lea     rbp, [rsp-200h]
0x140021a78  sub     rsp, 300h
0x140021a7f  mov     rax, cs:__security_cookie
0x140021a86  xor     rax, rsp
0x140021a89  mov     [rbp+230h+var_40], rax
0x140021a90  mov     rbx, [rbp+230h+arg_20]
0x140021a97  xorps   xmm0, xmm0
0x140021a9a  mov     [rbp+230h+psz], rcx
0x140021a9e  xor     eax, eax
0x140021aa0  xor     ecx, ecx
0x140021aa2  mov     [rbp+230h+var_2B0], r9d
0x140021aa6  mov     r14d, ecx
0x140021aa9  mov     [rsp+330h+var_2C0], rcx
0x140021aae  mov     r13, [rbx]
0x140021ab1  mov     r15, r8
0x140021ab4  mov     [rsp+330h+var_2B8], ecx
0x140021ab8  mov     edi, edx
0x140021aba  mov     [rbp+230h+var_288], rcx
0x140021abe  mov     esi, 100h
0x140021ac3  mov     [rbp+230h+var_280], ecx
0x140021ac6  mov     r8d, esi; Size
0x140021ac9  mov     [rbp+230h+var_274], cl
0x140021acc  xor     edx, edx; Val
0x140021ace  lea     rcx, [rbp+230h+var_240]; void *
0x140021ad2  mov     [rbp+230h+var_260], eax
0x140021ad5  mov     r12d, r9d
0x140021ad8  mov     [rbp+230h+var_248], eax
0x140021adb  movups  xmmword ptr [rbp+230h+var_270], xmm0
0x140021adf  mov     dword ptr [rbp+230h+var_278], 0F77F0300h
0x140021ae6  movups  xmmword ptr [rbp+230h+var_258], xmm0
0x140021aea  call    memset
0x140021aef  mov     r8d, esi; Size
0x140021af2  mov     [rbp+230h+var_2A4], esi
0x140021af5  xor     edx, edx; Val
0x140021af7  lea     rcx, [rbp+230h+var_140]; void *
0x140021afe  call    memset
0x140021b03  mov     rcx, [rbp+230h+psz]; psz
0x140021b07  lea     r8, [rbp+230h+pcbLength]; pcbLength
0x140021b0b  mov     [rbp+230h+var_2A8], esi
0x140021b0e  mov     rsi, [rbx+8]
0x140021b12  mov     [rbp+230h+pcbLength], r14
0x140021b16  call    RtlStringCbLengthW
0x140021b1b  mov     ebx, eax
0x140021b1d  cmp     edi, 3
0x140021b20  jnz     loc_140021F80
0x140021b26  cmp     r12d, 14h
0x140021b2a  jb      loc_140021F80
0x140021b30  mov     rcx, 0FFFFF78000000014h
0x140021b3a  mov     rcx, [rcx]
0x140021b3d  mov     qword ptr [rbp+230h+var_290], rcx
0x140021b41  test    r15, r15
0x140021b44  jz      loc_140021F80
0x140021b4a  cmp     dword ptr [r15], 4D504350h
0x140021b51  jnz     loc_140021F80
0x140021b57  mov     ecx, [r15+4]
0x140021b5b  cmp     ecx, 14h
0x140021b5e  jb      loc_140021F80
0x140021b64  cmp     dword ptr [r15+8], 1
0x140021b69  jnz     loc_140021F80
0x140021b6f  mov     eax, [r15+0Ch]
0x140021b73  test    al, 1
0x140021b75  jnz     loc_140021F80
0x140021b7b  mov     r12d, [r15+10h]
0x140021b7f  lea     eax, [r12+rcx]
0x140021b83  cmp     [rbp+230h+var_2B0], eax
0x140021b86  jb      loc_140021F80
0x140021b8c  cmp     r12, 17h
0x140021b90  jb      loc_140021F80
0x140021b96  lea     rdi, [r15+rcx]
0x140021b9a  movzx   eax, byte ptr [rdi+14h]
0x140021b9e  movzx   r10d, byte ptr [rdi+16h]
0x140021ba3  movzx   ecx, byte ptr [rdi+13h]
0x140021ba7  add     r10d, 17h
0x140021bab  shl     ecx, 8
0x140021bae  add     ecx, eax
0x140021bb0  movzx   eax, byte ptr [rdi+15h]
0x140021bb4  shl     ecx, 8
0x140021bb7  add     ecx, eax
0x140021bb9  shl     ecx, 8
0x140021bbc  add     r10d, ecx
0x140021bbf  lea     rax, [r10+4]
0x140021bc3  cmp     r12, rax
0x140021bc6  jb      loc_140021F80
0x140021bcc  lea     eax, [r10+1]
0x140021bd0  movzx   r8d, byte ptr [rax+rdi]
0x140021bd5  movzx   eax, byte ptr [r10+rdi]
0x140021bda  shl     eax, 8
0x140021bdd  add     r8d, eax
0x140021be0  lea     eax, [r10+2]
0x140021be4  shl     r8d, 8
0x140021be8  movzx   eax, byte ptr [rax+rdi]
0x140021bec  add     r8d, eax
0x140021bef  lea     eax, [r10+3]
0x140021bf3  shl     r8d, 8
0x140021bf7  add     r8d, 4
0x140021bfb  movzx   edx, byte ptr [rax+rdi]
0x140021bff  add     r8d, r10d
0x140021c02  add     r8d, edx
0x140021c05  lea     rax, [r8+4]
0x140021c09  cmp     r12, rax
0x140021c0c  jb      loc_140021F80
0x140021c12  lea     eax, [r8+1]
0x140021c16  movzx   edx, byte ptr [rax+rdi]
0x140021c1a  movzx   eax, byte ptr [r8+rdi]
0x140021c1f  shl     eax, 8
0x140021c22  add     edx, eax
0x140021c24  lea     eax, [r8+2]
0x140021c28  shl     edx, 8
0x140021c2b  movzx   eax, byte ptr [rax+rdi]
0x140021c2f  add     edx, eax
0x140021c31  lea     eax, [r8+3]
0x140021c35  shl     edx, 8
0x140021c38  add     r8d, 4
0x140021c3c  movzx   ecx, byte ptr [rax+rdi]
0x140021c40  add     ecx, edx
0x140021c42  lea     eax, [rcx+r8]
0x140021c46  cmp     r12d, eax
0x140021c49  jb      loc_140021F80
0x140021c4f  mov     r9d, r8d
0x140021c52  lea     rax, [rbp+230h+var_258]
0x140021c56  mov     [rsp+330h+cbOutput], 14h; cbOutput
0x140021c5e  add     r9, rdi; unsigned __int8 *
0x140021c61  mov     [rsp+330h+pbOutput], rax; pbOutput
0x140021c66  xor     r8d, r8d; cbSecret
0x140021c69  mov     dword ptr [rsp+330h+var_310], ecx; unsigned int
0x140021c6d  xor     edx, edx; pbSecret
0x140021c6f  lea     rcx, aSha1; "SHA1"
0x140021c76  call    ?BCryptHashData@@YAJPEBGPEAEI1I1I@Z; BCryptHashData(ushort const *,uchar *,uint,uchar *,uint,uchar *,uint)
0x140021c7b  test    eax, eax
0x140021c7d  jnz     loc_140021F80
0x140021c83  mov     rcx, [r13+10h]; this
0x140021c87  lea     rdx, [rsp+330h+var_2C0]; void **
0x140021c8c  call    ?CreateContext@TpmDevice@@QEAAJPEAPEAX@Z; TpmDevice::CreateContext(void * *)
0x140021c91  mov     r14, [rsp+330h+var_2C0]
0x140021c96  mov     ebx, eax
0x140021c98  test    eax, eax
0x140021c9a  js      loc_140021F80
0x140021ca0  test    rdi, rdi
0x140021ca3  jz      loc_140021F7B
0x140021ca9  test    r12d, r12d
0x140021cac  jz      loc_140021F7B
0x140021cb2  lea     rax, [rsp+330h+var_2B8]
0x140021cb7  mov     r8d, 0C2h; unsigned __int16
0x140021cbd  mov     [rsp+330h+var_2D0], rax
0x140021cc2  mov     r9d, 41h ; 'A'; unsigned int
0x140021cc8  mov     [rsp+330h+var_2D8], rdi
0x140021ccd  lea     rax, aU32au8hpu32; "u32Au8hpu32"
0x140021cd4  mov     dword ptr [rsp+330h+var_2E0], r12d
0x140021cd9  mov     rdx, r14; struct TpmContext *
0x140021cdc  mov     dword ptr [rsp+330h+var_2E8], 40000000h; unsigned __int8
0x140021ce4  mov     rcx, r13; this
0x140021ce7  mov     [rsp+330h+var_2F0], rax; unsigned int
0x140021cec  lea     rax, [rbp+230h+var_270]
0x140021cf0  mov     [rsp+330h+var_2F8], 0; unsigned int
0x140021cf9  mov     qword ptr [rsp+330h+cbOutput], 0; unsigned int
0x140021d02  mov     dword ptr [rsp+330h+pbOutput], 14h; ULONG
0x140021d0a  mov     [rsp+330h+var_310], rax; unsigned int
0x140021d0f  call    ?ExecuteInternalCmd@TpmScheduler@@QEAAJPEAVTpmContext@@GIPEAEI1IPEBDZZ; TpmScheduler::ExecuteInternalCmd(TpmContext *,ushort,uint,uchar *,uint,uchar *,uint,char const *,...)
0x140021d14  mov     ebx, eax
0x140021d16  test    eax, eax
0x140021d18  js      loc_140021F80
0x140021d1e  mov     r8d, [rsp+330h+var_2B8]; unsigned int
0x140021d23  lea     rax, [rbp+230h+var_2A8]
0x140021d27  mov     [rsp+330h+var_2C8], rax; unsigned int *
0x140021d2c  lea     r9, [rbp+230h+var_270]; unsigned __int8 *
0x140021d30  lea     rax, [rbp+230h+var_140]
0x140021d37  mov     rdx, r14; struct TpmContext *
0x140021d3a  mov     [rsp+330h+var_2D0], rax; unsigned __int8 *
0x140021d3f  mov     rcx, r13; this
0x140021d42  lea     rax, [rbp+230h+var_2A4]
0x140021d46  mov     [rsp+330h+var_2D8], rax; unsigned int *
0x140021d4b  lea     rax, [rbp+230h+var_240]
0x140021d4f  mov     [rsp+330h+var_2E0], rax; unsigned __int8 *
0x140021d54  lea     rax, [rbp+230h+var_278]
0x140021d58  mov     [rsp+330h+var_2F8], rax; unsigned __int8 *
0x140021d5d  lea     rax, [rbp+230h+var_290]
0x140021d61  mov     [rsp+330h+pbOutput], rax; unsigned __int8 *
0x140021d66  call    ?Quote2@TpmScheduler@@AEAAJPEAVTpmContext@@IPEAEIPEBEI2IE1PEAI13@Z; TpmScheduler::Quote2(TpmContext *,uint,uchar *,uint,uchar const *,uint,uchar const *,uint,uchar,uchar *,uint *,uchar *,uint *)
0x140021d6b  mov     r8d, [rsp+330h+var_2B8]; unsigned int
0x140021d70  mov     rdx, r14; struct TpmContext *
0x140021d73  mov     rcx, r13; this
0x140021d76  mov     ebx, eax
0x140021d78  call    ?FlushSpecific@TpmScheduler@@AEAAJPEAVTpmContext@@II@Z; TpmScheduler::FlushSpecific(TpmContext *,uint,uint)
0x140021d7d  mov     [rsp+330h+var_2B8], 0
0x140021d85  test    ebx, ebx
0x140021d87  js      loc_140021F9A
0x140021d8d  mov     rcx, [r13+10h]; this
0x140021d91  mov     rdx, r14; void *
0x140021d94  call    ?DeleteContext@TpmDevice@@QEAAXPEAX@Z; TpmDevice::DeleteContext(void *)
0x140021d99  xor     r14d, r14d
0x140021d9c  mov     dword ptr [rsp+330h+var_2C0], 0C0010004h
0x140021da4  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021da9  mov     rcx, rsi; this
0x140021dac  lea     r8d, [r14+4]; unsigned int
0x140021db0  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021db5  mov     ebx, eax
0x140021db7  test    eax, eax
0x140021db9  js      loc_140021F80
0x140021dbf  mov     r12d, [rbp+230h+var_2B0]
0x140021dc3  lea     r8d, [r14+8]; unsigned int
0x140021dc7  mov     edi, [rbp+230h+var_2A4]
0x140021dca  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021dcf  mov     r15d, [rbp+230h+var_2A8]
0x140021dd3  lea     ecx, [r12+20h]
0x140021dd8  add     rcx, r15
0x140021ddb  lea     rax, [rdi+16h]
0x140021ddf  add     rcx, rax
0x140021de2  mov     [rsp+330h+var_2C0], rcx
0x140021de7  mov     rcx, rsi; this
0x140021dea  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021def  mov     ebx, eax
0x140021df1  test    eax, eax
0x140021df3  js      loc_140021F80
0x140021df9  lea     r8d, [r14+4]; unsigned int
0x140021dfd  mov     dword ptr [rsp+330h+var_2C0], 80080003h
0x140021e05  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021e0a  mov     rcx, rsi; this
0x140021e0d  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021e12  mov     ebx, eax
0x140021e14  test    eax, eax
0x140021e16  js      loc_140021F80
0x140021e1c  lea     eax, [r12+2]
0x140021e21  mov     rcx, rsi; this
0x140021e24  lea     r12d, [r14+4]
0x140021e28  mov     dword ptr [rsp+330h+var_2C0], eax
0x140021e2c  mov     r8d, r12d; unsigned int
0x140021e2f  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021e34  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021e39  mov     ebx, eax
0x140021e3b  test    eax, eax
0x140021e3d  js      loc_140021F80
0x140021e43  mov     r8d, dword ptr [rbp+230h+pcbLength]; unsigned int
0x140021e47  mov     rcx, rsi; this
0x140021e4a  mov     rdx, [rbp+230h+psz]; void *
0x140021e4e  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021e53  mov     ebx, eax
0x140021e55  test    eax, eax
0x140021e57  js      loc_140021F80
0x140021e5d  xor     eax, eax
0x140021e5f  lea     r8d, [r14+2]; unsigned int
0x140021e63  lea     rdx, [rbp+230h+var_2B0]; void *
0x140021e67  mov     word ptr [rbp+230h+var_2B0], ax
0x140021e6b  mov     rcx, rsi; this
0x140021e6e  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021e73  mov     ebx, eax
0x140021e75  test    eax, eax
0x140021e77  js      loc_140021F80
0x140021e7d  mov     r8d, r12d; unsigned int
0x140021e80  mov     dword ptr [rsp+330h+var_2C0], 80080004h
0x140021e88  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021e8d  mov     rcx, rsi; this
0x140021e90  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021e95  mov     ebx, eax
0x140021e97  test    eax, eax
0x140021e99  js      loc_140021F80
0x140021e9f  mov     r8d, r12d; unsigned int
0x140021ea2  mov     dword ptr [rsp+330h+var_2C0], 14h
0x140021eaa  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021eaf  mov     rcx, rsi; this
0x140021eb2  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021eb7  mov     ebx, eax
0x140021eb9  test    eax, eax
0x140021ebb  js      loc_140021F80
0x140021ec1  lea     r8d, [r14+14h]; unsigned int
0x140021ec5  mov     rcx, rsi; this
0x140021ec8  lea     rdx, [rbp+230h+var_258]; void *
0x140021ecc  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021ed1  mov     ebx, eax
0x140021ed3  test    eax, eax
0x140021ed5  js      loc_140021F80
0x140021edb  mov     r8d, r12d; unsigned int
0x140021ede  mov     dword ptr [rsp+330h+var_2C0], 80080001h
0x140021ee6  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021eeb  mov     rcx, rsi; this
0x140021eee  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021ef3  mov     ebx, eax
0x140021ef5  test    eax, eax
0x140021ef7  js      loc_140021F80
0x140021efd  mov     r8d, r12d; unsigned int
0x140021f00  mov     dword ptr [rsp+330h+var_2C0], edi
0x140021f04  lea     rdx, [rsp+330h+var_2C0]; void *
0x140021f09  mov     rcx, rsi; this
0x140021f0c  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021f11  mov     ebx, eax
0x140021f13  test    eax, eax
0x140021f15  js      short loc_140021F80
0x140021f17  mov     r8d, edi; unsigned int
0x140021f1a  lea     rdx, [rbp+230h+var_240]; void *
0x140021f1e  mov     rcx, rsi; this
0x140021f21  call    ?Append@BufferAccessor@@QEAAJPEBXI@Z; BufferAccessor::Append(void const *,uint)
0x140021f26  mov     ebx, eax
0x140021f28  test    eax, eax
  ... truncated ...
```
