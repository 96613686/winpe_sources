# ClCertAccessCheck

- ea: `0x180035dec`
- end: `0x18003635b`
- name: `ClCertAccessCheck`
- size: `1391`
- prototype: `__int64 __fastcall(unsigned int, ULONG *, unsigned int, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022440`

## callees

- `0x1800214a4`
- `0x1800268d8`
- `0x180035dec`
- `0x180036388`
- `0x1800363c8`
- `0x1800368e4`
- `0x180036fb8`
- `0x180037510`
- `0x18003756c`
- `0x180037f58`
- `0x1800385a4`
- `0x180038d98`
- `0x180039e24`
- `0x18003b31c`
- `0x18004280c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035eb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035eb1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035e44`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035e44`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800362a6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800362a6`

## pseudocode

```c
__int64 __fastcall ClCertAccessCheck(
        unsigned int a1,
        ULONG *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  int v7; // r14d
  __int64 v8; // rdi
  char v9; // si
  __int64 v10; // r13
  int v11; // ebx
  int v12; // edx
  int v13; // r8d
  __int64 v15; // r12
  __int64 v16; // r15
  _QWORD *v17; // rsi
  ULONG CertificateProperties; // ebx
  __int64 v19; // rbx
  NTSTATUS v20; // edi
  unsigned __int64 v21; // r9
  char v22; // cl
  ULONG *v23; // rdi
  __int64 i; // r10
  UCHAR *v25; // rcx
  ULONG v26; // edx
  UCHAR *v27; // rax
  __int64 j; // r13
  int v29; // r8d
  __int64 v30; // r9
  __int64 v31; // rbx
  __int64 v32; // r11
  __int64 v33; // r9
  __int64 k; // rdi
  char v35; // [rsp+58h] [rbp-51h] BYREF
  char v36; // [rsp+59h] [rbp-50h]
  char v37; // [rsp+5Ah] [rbp-4Fh]
  __int64 v38; // [rsp+60h] [rbp-49h] BYREF
  __int64 v39; // [rsp+68h] [rbp-41h] BYREF
  int v40; // [rsp+70h] [rbp-39h]
  __int64 v41; // [rsp+78h] [rbp-31h]
  _QWORD *v42; // [rsp+80h] [rbp-29h]
  unsigned __int64 v43; // [rsp+88h] [rbp-21h]
  __int64 v44; // [rsp+90h] [rbp-19h]
  __int64 v45; // [rsp+98h] [rbp-11h]

  v7 = dword_18005E4CC;
  v8 = a4;
  v9 = a3;
  v10 = a1;
  v11 = (int)a2;
  v39 = 0;
  if ( !InitOnceExecuteOnce(&ClCertInitOnce, ClCertInitOnceFn, 0, 0) )
    return 1359;
  v15 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qLLS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v11, v9, v10, v8);
  }
  v17 = LocalAlloc(0x40u, 40 * v10);
  if ( v17 )
  {
    if ( v7 )
    {
      v15 = ClCertAceListAlloc(2 * v10);
      if ( !v15 || (v16 = ClCertAceListAlloc(2 * v10)) == 0 )
      {
        CertificateProperties = 8;
LABEL_61:
        CertificateProperties = ClCertWriteAuditEvents(
                                  CertificateProperties,
                                  v8,
                                  (_DWORD)v17,
                                  v10,
                                  v15,
                                  v16,
                                  a5,
                                  a6,
                                  a7);
        goto LABEL_62;
      }
    }
    v19 = 0;
    do
    {
      v20 = ClCertDuplicateHashHandle(&xmmword_18005C830[(unsigned int)v19], &v39 + v19);
      if ( v20 < 0 )
      {
        ClCertDestroyHashHandle(v39);
        v39 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
            v20,
            a4);
        }
        CertificateProperties = RtlNtStatusToDosErrorNoTeb(v20);
        goto LABEL_59;
      }
      v19 = (unsigned int)(v19 + 1);
    }
    while ( !(_DWORD)v19 );
    v21 = (unsigned __int64)a2;
    CertificateProperties = 0;
    v22 = 0;
    v37 = 0;
    v36 = 0;
    v23 = a2;
    for ( i = 0; ; i = (unsigned int)(v40 + 1) )
    {
      v40 = i;
      if ( (unsigned int)i >= (unsigned int)v10 )
        break;
      v35 = 0;
      v38 = 0;
      if ( v21 > (unsigned __int64)v23
        || !a3
        || (v25 = (UCHAR *)(v23 + 1), (unsigned __int64)(v23 + 1) >= v21 + a3)
        || (v26 = *v23) == 0
        || (v45 = *v23, v27 = &v25[v26], v21 >= (unsigned __int64)v27)
        || (unsigned __int64)v27 > v21 + a3 )
      {
        CertificateProperties = 87;
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_59;
      }
      v44 = (unsigned int)i;
      v42 = &v17[5 * i];
      CertificateProperties = ClCertGetCertificateProperties(v25, v26, (__int64)v42);
      if ( CertificateProperties )
        goto LABEL_59;
      for ( j = 0; !(_DWORD)j; j = 1 )
      {
        v43 = (unsigned __int64)&v38 & -(__int64)(v7 != 0);
        v29 = dword_18005C7A8[j];
        v30 = v17[4 * v44 + 4 + v44 + j];
        v41 = v44 + j + 4 * v44;
        CertificateProperties = ClCertCheckCertificateAccess(a4, 1, v29, v30, v43, (__int64)&v35);
        if ( CertificateProperties )
          goto LABEL_58;
        v37 |= v35;
        v31 = v41;
        v32 = 0;
        if ( v7 && v35 )
        {
          ClCertAceListAdd(v15, (unsigned int)dword_18005C7A8[j], v17[v41 + 4], v38);
          v38 = 0;
        }
        CertificateProperties = ClCertCheckCertificateAccess(
                                  a4,
                                  0,
                                  dword_18005C7A8[v32],
                                  v17[v31 + 4],
                                  v43,
                                  (__int64)&v35);
        if ( CertificateProperties )
          goto LABEL_58;
        v36 |= v35;
        if ( v7 && v35 )
        {
          ClCertAceListAdd(v16, (unsigned int)dword_18005C7A8[j], v17[v41 + 4], v38);
          v38 = 0;
        }
      }
      v33 = v42[3];
      v43 = (unsigned __int64)&v38 & -(__int64)(v7 != 0);
      CertificateProperties = ClCertCheckCertificateAccess(a4, 1, 1, v33, v43, (__int64)&v35);
      if ( CertificateProperties )
        goto LABEL_58;
      v37 |= v35;
      if ( v7 && v35 )
      {
        ClCertAceListAdd(v15, CertificateProperties + 1, v42[3], v38);
        v38 = 0;
      }
      CertificateProperties = ClCertCheckCertificateAccess(a4, 0, 1, v42[3], v43, (__int64)&v35);
      if ( CertificateProperties )
      {
LABEL_58:
        LODWORD(v10) = a1;
        goto LABEL_59;
      }
      v22 = v35 | v36;
      v36 |= v35;
      if ( v7 && v35 )
      {
        ClCertAceListAdd(v16, CertificateProperties + 1, v42[3], v38);
        v22 = v36;
      }
      LODWORD(v10) = a1;
      v23 = (ULONG *)((char *)v23 + v45 + 4);
      v21 = (unsigned __int64)a2;
    }
    if ( v37 || !v22 )
      CertificateProperties = -1067646969;
LABEL_59:
    LODWORD(v8) = a4;
  }
  else
  {
    CertificateProperties = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v8);
    }
  }
  if ( v7 )
    goto LABEL_61;
LABEL_62:
  ClCertDestroyHashHandle(v39);
  v39 = 0;
  if ( v15 )
    ClCertAceListFree(v15);
  if ( v16 )
    ClCertAceListFree(v16);
  if ( v17 )
  {
    for ( k = 0; (unsigned int)k < (unsigned int)v10; k = (unsigned int)(k + 1) )
      ClCertFreeCertificateProperties(&v17[5 * k]);
    ClCertLocalFree(v17);
  }
  return CertificateProperties;
}

```

## disassembly

```asm
0x180035dec  mov     rax, rsp
0x180035def  mov     [rax+20h], r9
0x180035df3  mov     [rax+18h], r8d
0x180035df7  mov     [rax+10h], rdx
0x180035dfb  mov     [rax+8], ecx
0x180035dfe  push    rbp
0x180035dff  push    rbx
0x180035e00  push    rsi
0x180035e01  push    rdi
0x180035e02  push    r12
0x180035e04  push    r13
0x180035e06  push    r14
0x180035e08  push    r15
0x180035e0a  lea     rbp, [rax-47h]
0x180035e0e  sub     rsp, 0A8h
0x180035e15  mov     r14d, cs:dword_18005E4CC
0x180035e1c  mov     rdi, r9
0x180035e1f  mov     esi, r8d
0x180035e22  mov     r13d, ecx
0x180035e25  mov     rbx, rdx
0x180035e28  mov     [rbp+3Fh+var_80], 0
0x180035e30  xor     r9d, r9d; Context
0x180035e33  lea     rdx, ClCertInitOnceFn; InitFn
0x180035e3a  xor     r8d, r8d; Parameter
0x180035e3d  lea     rcx, ClCertInitOnce; InitOnce
0x180035e44  call    cs:__imp_InitOnceExecuteOnce
0x180035e4a  test    eax, eax
0x180035e4c  jnz     short loc_180035E58
0x180035e4e  mov     eax, 54Fh
0x180035e53  jmp     loc_180036347
0x180035e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e5f  lea     rax, WPP_GLOBAL_Control
0x180035e66  xor     r12d, r12d
0x180035e69  xor     r15d, r15d
0x180035e6c  cmp     rcx, rax
0x180035e6f  jz      short loc_180035E9A
0x180035e71  test    dword ptr [rcx+1Ch], 800h
0x180035e78  jz      short loc_180035E9A
0x180035e7a  cmp     byte ptr [rcx+19h], 2
0x180035e7e  jb      short loc_180035E9A
0x180035e80  mov     rcx, [rcx+10h]
0x180035e84  mov     r9, rbx
0x180035e87  mov     [rsp+0E0h+var_B0], rdi
0x180035e8c  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180035e91  mov     dword ptr [rsp+0E0h+var_C0], esi
0x180035e95  call    WPP_SF_qLLS
0x180035e9a  lea     rdx, ds:0[r13*4]
0x180035ea2  mov     ecx, 40h ; '@'; uFlags
0x180035ea7  add     rdx, r13
0x180035eaa  mov     rbx, r13
0x180035ead  shl     rdx, 3; uBytes
0x180035eb1  call    cs:__imp_LocalAlloc
0x180035eb7  mov     rsi, rax
0x180035eba  test    rax, rax
0x180035ebd  jnz     short loc_180035F0B
0x180035ebf  lea     ebx, [rax+8]
0x180035ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ec9  lea     rax, WPP_GLOBAL_Control
0x180035ed0  cmp     rcx, rax
0x180035ed3  jz      loc_1800362B8
0x180035ed9  test    dword ptr [rcx+1Ch], 800h
0x180035ee0  jz      loc_1800362B8
0x180035ee6  cmp     byte ptr [rcx+19h], 1
0x180035eea  jb      loc_1800362B8
0x180035ef0  mov     rcx, [rcx+10h]
0x180035ef4  lea     edx, [rsi+0Ch]
0x180035ef7  mov     r9, rdi
0x180035efa  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180035f01  call    WPP_SF_S
0x180035f06  jmp     loc_1800362B8
0x180035f0b  test    r14d, r14d
0x180035f0e  jz      short loc_180035F3D
0x180035f10  add     rbx, rbx
0x180035f13  mov     rcx, rbx
0x180035f16  call    ClCertAceListAlloc
0x180035f1b  mov     r12, rax
0x180035f1e  test    rax, rax
0x180035f21  jnz     short loc_180035F2D
0x180035f23  mov     ebx, 8
0x180035f28  jmp     loc_1800362BD
0x180035f2d  mov     rcx, rbx
0x180035f30  call    ClCertAceListAlloc
0x180035f35  mov     r15, rax
0x180035f38  test    rax, rax
0x180035f3b  jz      short loc_180035F23
0x180035f3d  xor     ebx, ebx
0x180035f3f  lea     rax, xmmword_18005C830
0x180035f46  mov     ecx, ebx
0x180035f48  shl     rcx, 4
0x180035f4c  lea     rdx, [rbp+3Fh+var_80]
0x180035f50  add     rcx, rax
0x180035f53  lea     rdx, [rdx+rbx*8]
0x180035f57  call    ClCertDuplicateHashHandle
0x180035f5c  mov     edi, eax
0x180035f5e  test    eax, eax
0x180035f60  js      loc_180036250
0x180035f66  inc     ebx
0x180035f68  cmp     ebx, 1
0x180035f6b  jb      short loc_180035F3F
0x180035f6d  mov     r9, [rbp+3Fh+arg_8]
0x180035f71  xor     ebx, ebx
0x180035f73  xor     cl, cl
0x180035f75  mov     [rbp+3Fh+var_8E], bl
0x180035f78  mov     [rbp+3Fh+var_8F], cl
0x180035f7b  mov     rdi, r9
0x180035f7e  xor     r10d, r10d
0x180035f81  mov     [rbp+3Fh+var_78], r10d
0x180035f85  cmp     r10d, r13d
0x180035f88  jnb     loc_18003623F
0x180035f8e  mov     [rbp+3Fh+var_90], 0
0x180035f92  mov     [rbp+3Fh+var_88], 0
0x180035f9a  cmp     r9, rdi
0x180035f9d  ja      loc_180036233
0x180035fa3  mov     eax, [rbp+3Fh+arg_10]
0x180035fa6  test    eax, eax
0x180035fa8  jz      loc_180036233
0x180035fae  lea     rcx, [rdi+4]; pbInput
0x180035fb2  lea     r8, [r9+rax]
0x180035fb6  cmp     rcx, r8
0x180035fb9  jnb     loc_180036233
0x180035fbf  mov     edx, [rdi]; cbInput
0x180035fc1  test    edx, edx
0x180035fc3  jz      loc_180036224
0x180035fc9  mov     eax, edx
0x180035fcb  mov     [rbp+3Fh+var_50], rdx
0x180035fcf  add     rax, rcx
0x180035fd2  cmp     r9, rax
0x180035fd5  jnb     loc_180036224
0x180035fdb  cmp     rax, r8
0x180035fde  ja      loc_180036224
0x180035fe4  mov     eax, r10d
0x180035fe7  lea     r8, [rbp+3Fh+var_80]
0x180035feb  mov     [rbp+3Fh+var_58], rax
0x180035fef  mov     r9d, r14d
0x180035ff2  lea     rax, [r10+r10*4]
0x180035ff6  lea     rax, [rsi+rax*8]
0x180035ffa  mov     [rbp+3Fh+var_68], rax
0x180035ffe  mov     [rsp+0E0h+var_C0], rax; __int64
0x180036003  call    ClCertGetCertificateProperties
0x180036008  mov     ebx, eax
0x18003600a  test    eax, eax
0x18003600c  jnz     loc_1800362B4
0x180036012  xor     r13d, r13d
0x180036015  lea     r10d, [rax+1]
0x180036019  mov     eax, r14d
0x18003601c  cmp     r13d, r10d
0x18003601f  jnb     loc_180036135
0x180036025  mov     r8, [rbp+3Fh+var_58]
0x180036029  lea     r11, dword_18005C7A8
0x180036030  mov     rcx, [rbp+3Fh+arg_18]
0x180036034  neg     eax
0x180036036  lea     rax, [rbp+3Fh+var_88]
0x18003603a  sbb     rdx, rdx
0x18003603d  and     rdx, rax
0x180036040  lea     rax, ds:0[r8*4]
0x180036048  add     rax, r13
0x18003604b  mov     [rbp+3Fh+var_60], rdx
0x18003604f  add     rax, r8
0x180036052  lea     r8, [rbp+3Fh+var_90]
0x180036056  mov     [rsp+0E0h+var_B8], r8
0x18003605b  mov     r8d, [r11+r13*4]
0x18003605f  mov     [rsp+0E0h+var_C0], rdx
0x180036064  mov     edx, r10d
0x180036067  mov     r9, [rsi+rax*8+20h]
0x18003606c  mov     [rbp+3Fh+var_70], rax
0x180036070  call    ClCertCheckCertificateAccess
0x180036075  mov     ebx, eax
0x180036077  test    eax, eax
0x180036079  jnz     loc_1800362B0
0x18003607f  mov     cl, [rbp+3Fh+var_90]
0x180036082  or      [rbp+3Fh+var_8E], cl
0x180036085  mov     rbx, [rbp+3Fh+var_70]
0x180036089  mov     r11d, r13d
0x18003608c  test    r14d, r14d
0x18003608f  jz      short loc_1800360B9
0x180036091  test    cl, cl
0x180036093  jz      short loc_1800360B9
0x180036095  mov     r9, [rbp+3Fh+var_88]
0x180036099  lea     rdx, dword_18005C7A8
0x1800360a0  mov     r8, [rsi+rbx*8+20h]
0x1800360a5  mov     rcx, r12
0x1800360a8  mov     edx, [rdx+r13*4]
0x1800360ac  call    ClCertAceListAdd
0x1800360b1  mov     [rbp+3Fh+var_88], 0
0x1800360b9  mov     r9, [rsi+rbx*8+20h]
0x1800360be  lea     rax, [rbp+3Fh+var_90]
0x1800360c2  mov     rcx, [rbp+3Fh+arg_18]
0x1800360c6  xor     edx, edx
0x1800360c8  mov     [rsp+0E0h+var_B8], rax
0x1800360cd  mov     rax, [rbp+3Fh+var_60]
0x1800360d1  mov     [rsp+0E0h+var_C0], rax
0x1800360d6  lea     rax, dword_18005C7A8
0x1800360dd  mov     r8d, [rax+r11*4]
0x1800360e1  call    ClCertCheckCertificateAccess
0x1800360e6  mov     ebx, eax
0x1800360e8  test    eax, eax
0x1800360ea  jnz     loc_1800362B0
0x1800360f0  mov     al, [rbp+3Fh+var_90]
0x1800360f3  or      [rbp+3Fh+var_8F], al
0x1800360f6  test    r14d, r14d
0x1800360f9  jz      short loc_180036127
0x1800360fb  test    al, al
0x1800360fd  jz      short loc_180036127
0x1800360ff  mov     rax, [rbp+3Fh+var_70]
0x180036103  lea     rdx, dword_18005C7A8
0x18003610a  mov     r9, [rbp+3Fh+var_88]
0x18003610e  mov     rcx, r15
0x180036111  mov     edx, [rdx+r13*4]
0x180036115  mov     r8, [rsi+rax*8+20h]
0x18003611a  call    ClCertAceListAdd
0x18003611f  mov     [rbp+3Fh+var_88], 0
0x180036127  mov     r10d, 1
0x18003612d  add     r13d, r10d
0x180036130  jmp     loc_180036019
0x180036135  mov     r9, [rbp+3Fh+var_68]
0x180036139  lea     rcx, [rbp+3Fh+var_88]
0x18003613d  mov     r13, [rbp+3Fh+arg_18]
0x180036141  neg     eax
0x180036143  mov     r8d, r10d
0x180036146  mov     edx, r10d
0x180036149  sbb     rax, rax
0x18003614c  mov     r9, [r9+18h]
0x180036150  and     rax, rcx
0x180036153  lea     rcx, [rbp+3Fh+var_90]
0x180036157  mov     [rbp+3Fh+var_60], rax
0x18003615b  mov     [rsp+0E0h+var_B8], rcx
0x180036160  mov     rcx, r13
0x180036163  mov     [rsp+0E0h+var_C0], rax
0x180036168  call    ClCertCheckCertificateAccess
0x18003616d  mov     ebx, eax
0x18003616f  test    eax, eax
0x180036171  jnz     loc_1800362B0
0x180036177  mov     cl, [rbp+3Fh+var_90]
0x18003617a  or      [rbp+3Fh+var_8E], cl
0x18003617d  test    r14d, r14d
0x180036180  jz      short loc_1800361A5
0x180036182  test    cl, cl
0x180036184  jz      short loc_1800361A5
0x180036186  mov     rax, [rbp+3Fh+var_68]
0x18003618a  lea     edx, [rbx+1]
0x18003618d  mov     r9, [rbp+3Fh+var_88]
0x180036191  mov     rcx, r12
0x180036194  mov     r8, [rax+18h]
0x180036198  call    ClCertAceListAdd
0x18003619d  mov     [rbp+3Fh+var_88], 0
0x1800361a5  lea     rax, [rbp+3Fh+var_90]
0x1800361a9  xor     edx, edx
0x1800361ab  mov     [rsp+0E0h+var_B8], rax
0x1800361b0  mov     rcx, r13
0x1800361b3  mov     rax, [rbp+3Fh+var_60]
0x1800361b7  mov     [rsp+0E0h+var_C0], rax
0x1800361bc  mov     rax, [rbp+3Fh+var_68]
0x1800361c0  lea     r8d, [rdx+1]
0x1800361c4  mov     r9, [rax+18h]
0x1800361c8  call    ClCertCheckCertificateAccess
0x1800361cd  mov     ebx, eax
0x1800361cf  test    eax, eax
0x1800361d1  jnz     loc_1800362B0
0x1800361d7  mov     cl, [rbp+3Fh+var_8F]
0x1800361da  mov     al, [rbp+3Fh+var_90]
0x1800361dd  or      cl, al
0x1800361df  mov     [rbp+3Fh+var_8F], cl
0x1800361e2  test    r14d, r14d
0x1800361e5  jz      short loc_180036205
0x1800361e7  test    al, al
0x1800361e9  jz      short loc_180036205
0x1800361eb  mov     rax, [rbp+3Fh+var_68]
0x1800361ef  lea     edx, [rbx+1]
0x1800361f2  mov     r9, [rbp+3Fh+var_88]
0x1800361f6  mov     rcx, r15
0x1800361f9  mov     r8, [rax+18h]
0x1800361fd  call    ClCertAceListAdd
0x180036202  mov     cl, [rbp+3Fh+var_8F]
0x180036205  mov     rax, [rbp+3Fh+var_50]
0x180036209  mov     r10d, [rbp+3Fh+var_78]
0x18003620d  add     rax, 4
0x180036211  mov     r13d, [rbp+3Fh+arg_0]
0x180036215  add     rdi, rax
0x180036218  mov     r9, [rbp+3Fh+arg_8]
0x18003621c  inc     r10d
0x18003621f  jmp     loc_180035F81
0x180036224  mov     ebx, 57h ; 'W'
0x180036229  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE", "The client certificate chain buffer is invalid: the certificate blob sizes must be greater than zero and memory accesses must be valid")
0x18003622e  jmp     loc_1800362B4
0x180036233  mov     ebx, 57h ; 'W'
0x180036238  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE", "The client certificate chain buffer is invalid: the buffer size must be greater than zero and memory accesses must be valid")
0x18003623d  jmp     short loc_1800362B4
0x18003623f  cmp     [rbp+3Fh+var_8E], 0
0x180036243  jnz     short loc_180036249
0x180036245  test    cl, cl
0x180036247  jnz     short loc_1800362B4
0x180036249  mov     ebx, 0C05D0007h
0x18003624e  jmp     short loc_1800362B4
0x180036250  mov     rcx, [rbp+3Fh+var_80]
0x180036254  call    ClCertDestroyHashHandle
0x180036259  mov     [rbp+3Fh+var_80], 0
0x180036261  mov     rcx, cs:WPP_GLOBAL_Control
0x180036268  lea     rax, WPP_GLOBAL_Control
0x18003626f  cmp     rcx, rax
0x180036272  jz      short loc_1800362A4
  ... truncated ...
```
