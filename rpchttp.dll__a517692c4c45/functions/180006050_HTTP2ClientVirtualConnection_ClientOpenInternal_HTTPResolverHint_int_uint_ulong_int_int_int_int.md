# HTTP2ClientVirtualConnection::ClientOpenInternal(HTTPResolverHint *,int,uint,ulong,int,int,int,int)

- ea: `0x180006050`
- end: `0x180007ba0`
- name: `?ClientOpenInternal@HTTP2ClientVirtualConnection@@AEAAJPEAVHTTPResolverHint@@HIKHHHH@Z`
- size: `6992`
- prototype: `__int64 __usercall@<rax>(HTTP2ClientVirtualConnection *__hidden this@<rcx>, struct HTTPResolverHint *@<rdx>, int@<r8d>, unsigned int@<r9d>, DWORD dwMilliseconds, int, int, int, int)`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x1800106b8`
- `0x1800168d0`

## callees

- `0x1800044dc`
- `0x180004bf8`
- `0x180005d50`
- `0x180006050`
- `0x18000a4ec`
- `0x18000adc4`
- `0x18000ae20`
- `0x18000bfe0`
- `0x18000eeec`
- `0x18000ef00`
- `0x18000f2bc`
- `0x180016e54`
- `0x180016e9c`
- `0x1800193d0`
- `0x18001941c`
- `0x18001977c`
- `0x1800197dc`
- `0x18001abd0`
- `0x18001ac1c`
- `0x18001ac8c`
- `0x18001b9b4`
- `0x18001bae0`
- `0x18001e524`
- `0x18001e5bc`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000784c`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a3e`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a72`
- `ntdll!RtlLeaveCriticalSection` at `0x180007b55`
- `ntdll!RtlLeaveCriticalSection` at `0x18000784c`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a3e`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a72`
- `ntdll!RtlLeaveCriticalSection` at `0x180007b55`
- `ntdll!RtlEnterCriticalSection` at `0x180007803`
- `ntdll!RtlEnterCriticalSection` at `0x180007b27`
- `ntdll!RtlEnterCriticalSection` at `0x180007803`
- `ntdll!RtlEnterCriticalSection` at `0x180007b27`
- `KERNEL32!Sleep` at `0x180006cfe`
- `KERNEL32!Sleep` at `0x180006cfe`
- `KERNEL32!CreateEventW` at `0x18000619c`
- `KERNEL32!CreateEventW` at `0x18000619c`
- `KERNEL32!WaitForSingleObject` at `0x180006b29`
- `KERNEL32!WaitForSingleObject` at `0x180006b29`
- `KERNEL32!CloseHandle` at `0x180007a7c`
- `KERNEL32!CloseHandle` at `0x180007b63`
- `KERNEL32!CloseHandle` at `0x180007a7c`
- `KERNEL32!CloseHandle` at `0x180007b63`
- `RPCRT4!I_RpcLogEvent` at `0x180006369`
- `RPCRT4!I_RpcLogEvent` at `0x18000647a`
- `RPCRT4!I_RpcLogEvent` at `0x1800065d4`
- `RPCRT4!I_RpcLogEvent` at `0x180006614`
- `RPCRT4!I_RpcLogEvent` at `0x180006369`
- `RPCRT4!I_RpcLogEvent` at `0x18000647a`
- `RPCRT4!I_RpcLogEvent` at `0x1800065d4`
- `RPCRT4!I_RpcLogEvent` at `0x180006614`

## pseudocode

```c
__int64 __fastcall HTTP2ClientVirtualConnection::ClientOpenInternal(
        HTTP2ClientVirtualConnection *this,
        struct HTTPResolverHint *a2,
        __int64 a3,
        unsigned int a4,
        DWORD dwMilliseconds,
        int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  int v9; // r15d
  HANDLE v10; // r14
  struct HTTPResolverHint *v11; // r8
  int v13; // eax
  __int64 v14; // rcx
  int v15; // r12d
  int v16; // r13d
  unsigned int v17; // edi
  unsigned int *v18; // rdx
  unsigned int v19; // ebx
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  char *v23; // rcx
  int v24; // r9d
  HANDLE v25; // rcx
  struct HTTPResolverHint *v26; // rbx
  __int64 v27; // rcx
  int v28; // r14d
  int v29; // ebx
  int v30; // r8d
  BOOL v31; // r11d
  HTTP2ClientVirtualConnection *v32; // rax
  __int64 v33; // rdx
  HTTP2ClientVirtualConnection *v34; // rax
  int v35; // r8d
  unsigned int v36; // r9d
  HTTP2ClientVirtualConnection *v37; // rax
  struct HTTP2Channel *v38; // rax
  __int64 v39; // rbx
  unsigned int v40; // edi
  unsigned int v41; // eax
  HTTP2ClientVirtualConnection *v42; // rax
  struct HTTP2Channel *v43; // rax
  struct HTTP2Channel *v44; // r9
  __int64 v45; // rcx
  unsigned int v46; // edx
  __int64 v47; // rcx
  struct HTTP2SendContext *v48; // rax
  struct HTTP2SendContext *v49; // r14
  struct HTTP2SendContext *v50; // rax
  struct HTTP2SendContext *v51; // rdi
  unsigned int v52; // ebx
  unsigned int OutChannelChosenScheme; // eax
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rax
  unsigned int v57; // r9d
  __int64 v58; // rcx
  int v59; // r15d
  int v60; // r14d
  __int64 v61; // rax
  BOOL v62; // r10d
  __int64 v63; // rax
  int IsKeepAlive; // edi
  HTTP2ClientVirtualConnection *v65; // rbx
  struct HTTP2Channel *v66; // rax
  __int64 v67; // rdx
  unsigned int v68; // eax
  bool v69; // zf
  int v70; // r9d
  int v71; // eax
  __int64 v72; // rax
  int v73; // r14d
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // edi
  HTTP2ClientVirtualConnection *v78; // rbx
  struct HTTP2Channel *v79; // rax
  __int64 v80; // rdx
  int v81; // eax
  unsigned int v82; // edi
  __int64 v83; // rax
  unsigned __int16 v84; // r8
  unsigned int v85; // r9d
  struct tagExtendedErrorInfo *v86; // rax
  unsigned int v87; // ecx
  unsigned __int16 v88; // r8
  unsigned int v89; // r9d
  unsigned int v90; // edx
  struct tagExtendedErrorInfo *v91; // rax
  struct tagExtendedErrorInfo *v92; // rax
  struct tagExtendedErrorInfo *v93; // rax
  __int64 v94; // rdx
  HTTP2ChannelPointer *v95; // r12
  struct HTTP2Channel *v96; // rax
  struct tagExtendedErrorInfo *v97; // rax
  struct tagExtendedErrorInfo *v98; // rax
  struct tagExtendedErrorInfo *v99; // rax
  struct tagExtendedErrorInfo *v100; // rax
  unsigned int v101; // r9d
  unsigned __int16 v102; // r8
  struct tagExtendedErrorInfo *v103; // rax
  unsigned int v104; // r14d
  struct tagExtendedErrorInfo *v105; // rax
  __int64 v106; // rdx
  unsigned int v108; // [rsp+28h] [rbp-E0h]
  unsigned int v109; // [rsp+28h] [rbp-E0h]
  int v110; // [rsp+78h] [rbp-90h]
  int v111; // [rsp+7Ch] [rbp-8Ch]
  int v112; // [rsp+80h] [rbp-88h]
  DWORD v113; // [rsp+84h] [rbp-84h]
  int v114; // [rsp+88h] [rbp-80h]
  BOOL v115; // [rsp+8Ch] [rbp-7Ch]
  int v116; // [rsp+98h] [rbp-70h]
  BOOL v117; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v118; // [rsp+A0h] [rbp-68h]
  unsigned int v119; // [rsp+A4h] [rbp-64h]
  DWORD v120; // [rsp+A8h] [rbp-60h]
  int v121; // [rsp+ACh] [rbp-5Ch]
  int v122; // [rsp+B0h] [rbp-58h]
  BOOL v123; // [rsp+B4h] [rbp-54h]
  unsigned int v124; // [rsp+B8h] [rbp-50h]
  int v125; // [rsp+BCh] [rbp-4Ch]
  int v126; // [rsp+C0h] [rbp-48h]
  int v127; // [rsp+C4h] [rbp-44h]
  unsigned int v128; // [rsp+C8h] [rbp-40h]
  DWORD v129; // [rsp+CCh] [rbp-3Ch]
  int v130; // [rsp+D0h] [rbp-38h]
  int v131; // [rsp+D4h] [rbp-34h]
  int v132; // [rsp+D8h] [rbp-30h]
  int v133; // [rsp+DCh] [rbp-2Ch]
  struct HTTP2Channel *v134; // [rsp+E0h] [rbp-28h] BYREF
  struct HTTP2Channel *v135; // [rsp+E8h] [rbp-20h] BYREF
  int v136; // [rsp+F0h] [rbp-18h]
  int v137; // [rsp+F4h] [rbp-14h]
  int v138; // [rsp+F8h] [rbp-10h]
  HTTP2ChannelPointer *v139; // [rsp+100h] [rbp-8h]
  HANDLE hHandle; // [rsp+108h] [rbp+0h]
  HTTP2ChannelPointer *v141; // [rsp+110h] [rbp+8h]
  int v142; // [rsp+158h] [rbp+50h]
  BOOL v144; // [rsp+168h] [rbp+60h]

  v9 = a8;
  v10 = 0;
  v134 = 0;
  v11 = a2;
  v135 = 0;
  if ( !a8 )
  {
    if ( a4 == 10 )
    {
      *((_DWORD *)this + 94) = -1;
    }
    else
    {
      v13 = (*((__int64 (__fastcall **)(_QWORD, struct HTTPResolverHint *, struct HTTPResolverHint *))pRuntimeImportTable
             + 19))(
              a4,
              a2,
              a2);
      v11 = a2;
      *((_DWORD *)this + 94) = v13;
    }
  }
  v14 = *((_QWORD *)this + 76);
  v15 = 7;
  v113 = 0;
  v16 = 7;
  v17 = 0;
  if ( !v14 )
  {
    v120 = 0;
    if ( a8 )
    {
      v111 = 1;
      LODWORD(v10) = 1;
      if ( a6 )
      {
        v15 = 1;
        goto LABEL_21;
      }
    }
    else
    {
      v111 = 0;
      v15 = 1;
    }
    v16 = 1;
    goto LABEL_21;
  }
  v18 = *(unsigned int **)(v14 + 24);
  if ( v18 && ((*(_BYTE *)(v14 + 8) & 2) != 0 || ((*v18 - 0x20000) & 0xFFFDFFFF) == 0) )
  {
    v17 = *v18;
    if ( a6 )
      v15 = (v17 & 0x20000) != 0 ? 2 : 4;
    if ( a7 )
      v16 = (v17 & 0x20000) != 0 ? 2 : 4;
  }
  if ( v17 == 2 && *((_DWORD *)v11 + 8) == 2 && (*(_BYTE *)(v14 + 8) & 1) == 0 )
  {
    v19 = 1764;
    goto LABEL_487;
  }
  v120 = v17;
  v111 = 0;
  v113 = v17;
LABEL_21:
  v128 = *((_DWORD *)this + 156);
  v129 = *((_DWORD *)this + 157);
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( !hHandle )
  {
    v19 = 14;
    v10 = 0;
    goto LABEL_487;
  }
  v133 = 0;
  if ( !a8 )
  {
    v19 = (*((__int64 (__fastcall **)(char *, __int64))pRuntimeImportTable + 3))((char *)this + 88, 16);
    if ( v19 )
      goto LABEL_423;
    if ( a6 )
    {
      v20 = (*((__int64 (__fastcall **)(char *, __int64))pRuntimeImportTable + 3))((char *)this + 160, 16);
      v125 = v19;
      goto LABEL_32;
    }
    v21 = 0;
LABEL_35:
    v124 = v21;
    v125 = 0;
    goto LABEL_36;
  }
  if ( !a6 )
  {
    v21 = *((_DWORD *)this + 68) ^ 1;
    goto LABEL_35;
  }
  v125 = *((_DWORD *)this + 48) ^ 1;
  v20 = (*((__int64 (__fastcall **)(char *, __int64))pRuntimeImportTable + 3))((char *)this + 16 * v125 + 160, 16);
LABEL_32:
  v19 = v20;
  v21 = 0;
  v124 = 0;
  if ( v19 )
    goto LABEL_423;
LABEL_36:
  v22 = a7;
  if ( a7 )
  {
    if ( a8 )
      v23 = (char *)this + 16 * v21 + 240;
    else
      v23 = (char *)this + 240;
    v19 = (*((__int64 (__fastcall **)(char *, __int64))pRuntimeImportTable + 3))(v23, 16);
    if ( v19 )
      goto LABEL_423;
    v22 = a7;
  }
  v24 = a6;
  v138 = 0;
  v137 = 0;
  v139 = 0;
  v141 = 0;
  v131 = 0;
  v112 = 0;
  v25 = hHandle;
  v118 = 87;
  v119 = 87;
  if ( a6 )
  {
    v116 = 1;
    *((_DWORD *)this + 104) = 997;
    *((_QWORD *)this + 50) = v25;
  }
  else
  {
    v116 = 0;
  }
  if ( (_DWORD)v22 )
  {
    v117 = 1;
    *((_DWORD *)this + 108) = 997;
    *((_QWORD *)this + 51) = v25;
  }
  else
  {
    v117 = 0;
  }
  v26 = a2;
  v27 = 5;
  v130 = 0;
  v127 = *((_DWORD *)a2 + 8);
  if ( v127 )
  {
    if ( v17 )
    {
      if ( (v17 & 0x20000) != 0 )
      {
        v15 = a6 != 0 ? 2 : 7;
        v29 = v22 != 0;
        v16 = (-v29 & 0xFFFFFFFB) + 7;
LABEL_61:
        v142 = v29;
        v26 = a2;
        goto LABEL_73;
      }
      if ( a6 )
      {
        v15 = 4;
        if ( a8 )
        {
          LODWORD(v10) = 1;
          v111 = 1;
        }
      }
      else
      {
        v15 = 7;
      }
      if ( (_DWORD)v22 )
      {
        v16 = 4;
        if ( a8 )
          LODWORD(v10) = 1;
        v111 = (int)v10;
        v29 = a8 == 0;
        goto LABEL_61;
      }
    }
    else
    {
      if ( a6 )
      {
        if ( v15 != 1 )
          v15 = 5;
      }
      else
      {
        v15 = 7;
      }
      if ( (_DWORD)v22 )
      {
        if ( v16 == 1 )
        {
          if ( !a8 )
          {
            v142 = 1;
LABEL_74:
            LOBYTE(v22) = 61;
            LOBYTE(v27) = 50;
            I_RpcLogEvent(v27, v22, this, 0, 3, 1, 0);
            v24 = a6;
            *((_DWORD *)this + 80) = 3;
            goto LABEL_75;
          }
          v142 = 0;
LABEL_75:
          if ( v15 != 4 && v15 != 1 || (v114 = 1, a8) )
            v114 = 0;
          if ( v16 != 4 && v16 != 1 || (v115 = 1, a8) )
            v115 = 0;
          if ( !v24 || v15 == 1 || v15 == 4 )
          {
            v28 = 0;
            v144 = 0;
          }
          else
          {
            v28 = 1;
            v144 = 1;
          }
          goto LABEL_88;
        }
        v16 = 5;
        v142 = 1;
LABEL_73:
        if ( !a8 )
          goto LABEL_74;
        goto LABEL_75;
      }
    }
    v142 = 0;
    v16 = 7;
    goto LABEL_73;
  }
  v15 = 0;
  v16 = 0;
  LOBYTE(v22) = 61;
  LOBYTE(v27) = 50;
  I_RpcLogEvent(v27, v22, this, 0, 20, 1, 0);
  *((_DWORD *)this + 80) = 20;
  v28 = 1;
  v144 = 1;
  v142 = 1;
  v114 = 0;
  v115 = 0;
LABEL_88:
  v30 = 0;
  v122 = v116;
  v31 = 0;
  v110 = 0;
  v123 = 0;
  v121 = 0;
  v126 = v117;
LABEL_90:
  while ( 2 )
  {
    if ( v31 )
    {
      if ( v9 )
        v32 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * v125);
      else
        v32 = this;
      v139 = (HTTP2ClientVirtualConnection *)((char *)v32 + 120);
      HTTP2ChannelPointer::FreeChannelPointer((HTTP2ClientVirtualConnection *)((char *)v32 + 120), 1, v9, 1, 0xC0021012);
      v30 = v110;
      *((_DWORD *)this + 104) = 997;
    }
    v33 = v124;
LABEL_96:
    if ( v30 )
    {
      if ( v9 )
        v34 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * (int)v33);
      else
        v34 = this;
      v141 = (HTTP2ClientVirtualConnection *)((char *)v34 + 200);
      HTTP2ChannelPointer::FreeChannelPointer((HTTP2ClientVirtualConnection *)((char *)v34 + 200), 1, v9, 1, 0xC0021012);
      *((_DWORD *)this + 108) = 997;
    }
    if ( v130 )
    {
      LOBYTE(v33) = 61;
      LOBYTE(v27) = 50;
      I_RpcLogEvent(v27, v33, this, 0, v131, 1, 0);
      *((_DWORD *)this + 80) = v131;
      v130 = 0;
    }
    LOBYTE(v33) = 43;
    I_RpcLogEvent(114, v33, this, 136, _InterlockedIncrement((volatile signed __int32 *)this + 149), 1, 1);
    if ( *((_DWORD *)this + 150) )
    {
      HTTP2ClientVirtualConnection::UnblockAborts(this);
      v133 = 0;
      goto LABEL_472;
    }
    v133 = 1;
    if ( v116 )
    {
      if ( !v127 )
        *((_DWORD *)v26 + 8) = 1;
      v19 = HTTP2ClientVirtualConnection::AllocateAndInitializeInChannel(
              this,
              (struct HTTPResolverHint *)v33,
              v35,
              v36,
              &v134);
      if ( !v127 )
        *((_DWORD *)a2 + 8) = 0;
      if ( v19 )
        goto LABEL_409;
      if ( v9 )
        HTTP2VirtualConnection::SetNonDefaultInChannel(this, v134);
      else
        HTTP2VirtualConnection::SetFirstInChannel(this, v134);
    }
    if ( !v117 )
      goto LABEL_122;
    if ( !v127 )
      *((_DWORD *)a2 + 8) = 2;
    v19 = HTTP2ClientVirtualConnection::AllocateAndInitializeOutChannel(
            this,
            (struct HTTPResolverHint *)v33,
            v35,
            v36,
            &v135);
    if ( !v127 )
      *((_DWORD *)a2 + 8) = 0;
    if ( v19 )
    {
LABEL_409:
      v51 = 0;
      v49 = 0;
      goto LABEL_415;
    }
    if ( v9 )
      HTTP2VirtualConnection::SetNonDefaultOutChannel(this, v135);
    else
      HTTP2VirtualConnection::SetFirstOutChannel(this, v135);
LABEL_122:
    if ( v121 || v122 || v114 != v121 || v28 )
    {
      if ( v9 )
        v37 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * v125);
      else
        v37 = this;
      v139 = (HTTP2ClientVirtualConnection *)((char *)v37 + 120);
      v38 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v37 + 120), v33);
      v134 = v38;
      v33 = (__int64)v38;
      if ( !v38 )
        goto LABEL_472;
      v137 = 1;
      if ( v121 )
      {
        (*(void (__fastcall **)(struct HTTP2Channel *))(*(_QWORD *)v38 + 64LL))(v38);
        v33 = (__int64)v134;
      }
      if ( v122 )
      {
        if ( !v15 || v15 == 5 || v17 == 0x20000 && v15 == 2 )
        {
          v39 = -1;
          v40 = v17 != 0x20000 ? 4 : 0;
          if ( v113 != 0x20000 )
            v39 = (__int64)byte_1800282E0;
          if ( !v127 )
            *((_DWORD *)a2 + 8) = 1;
        }
        else
        {
          v39 = 0;
          v40 = 0;
        }
        if ( !v9 )
          HTTP2PlugChannel::Unplug((HTTP2PlugChannel *)(v33 + 112));
        v41 = HTTP2ClientChannel::ClientOpen(
                (HTTP2ClientChannel *)dwMilliseconds,
                a2,
                "RPC_IN_DATA",
                0xBu,
                1,
                v9,
                *((struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W **)this + 76),
                v113,
                v128,
                (struct HTTP2Channel *)((char *)v134 + 568),
                dwMilliseconds,
                (const unsigned __int8 *)v39,
                v40);
        v19 = v41;
        if ( !v127 )
          *((_DWORD *)a2 + 8) = 0;
        if ( v41 )
        {
          if ( *((_DWORD *)this + 80) != 20 )
          {
            v51 = 0;
            v49 = 0;
            goto LABEL_416;
          }
          v28 = 0;
          *((_DWORD *)this + 104) = v41;
          v144 = 0;
          v114 = 0;
        }
      }
    }
    if ( !v123 && !v126 && !v115 && !v142 )
      goto LABEL_176;
    if ( v9 )
      v42 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * (int)v124);
    else
      v42 = this;
    v141 = (HTTP2ClientVirtualConnection *)((char *)v42 + 200);
    v43 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v42 + 200), v33);
    v135 = v43;
    v44 = v43;
    if ( !v43 )
    {
LABEL_472:
      v19 = -1073606638;
      goto LABEL_473;
    }
    v138 = 1;
    if ( v123 )
    {
      (*(void (__fastcall **)(struct HTTP2Channel *))(*(_QWORD *)v43 + 64LL))(v43);
      v44 = v135;
    }
    if ( v126 )
    {
      if ( !v16 || v16 == 5 || v120 == 0x20000 && v16 == 2 )
      {
        v45 = -1;
        v46 = v120 != 0x20000 ? 4 : 0;
        if ( v120 != 0x20000 )
          v45 = (__int64)byte_1800282E0;
        if ( !v127 )
          *((_DWORD *)a2 + 8) = 2;
      }
      else
      {
        v45 = 0;
        v46 = 0;
      }
      v19 = HTTP2ClientChannel::ClientOpen(
              (HTTP2ClientChannel *)dwMilliseconds,
              a2,
              "RPC_OUT_DATA",
              0xCu,
              0,
              v9,
              *((struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W **)this + 76),
              v120,
              v129,
              (struct HTTP2Channel *)((char *)v44 + 352),
              dwMilliseconds,
              (const unsigned __int8 *)v45,
              v46);
      if ( !v127 )
        *((_DWORD *)a2 + 8) = 0;
      if ( v19 )
      {
        if ( !v9 && *((_DWORD *)this + 80) == 20 && *((_DWORD *)this + 104) == 997 )
        {
          *((_DWORD *)this + 108) = v19;
          v115 = 0;
          v142 = 0;
          goto LABEL_176;
        }
LABEL_473:
        v51 = 0;
        v49 = 0;
        goto LABEL_415;
      }
    }
LABEL_176:
    HTTP2ClientVirtualConnection::UnblockAborts(this);
    v133 = 0;
    if ( v114 )
    {
      v48 = AllocateAndInitializeD1_B1(
              v47,
              (HTTP2ClientVirtualConnection *)((char *)this + 88),
              (HTTP2ClientVirtualConnection *)((char *)this + 160),
              DefaultChannelLifetime,
              v108,
              (struct HTTPResolverHint *)((char *)a2 + 122));
      v49 = v48;
      if ( !v48 )
      {
        v19 = 14;
        v51 = 0;
        v49 = 0;
        goto LABEL_415;
      }
      v19 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v134 + 8LL))(
              v134,
              v48);
      if ( v19 )
      {
        v51 = 0;
        goto LABEL_415;
      }
      v28 = v144;
    }
    if ( v115 )
    {
      v50 = AllocateAndInitializeD1_A1(
              v47,
              (HTTP2ClientVirtualConnection *)((char *)this + 88),
              (HTTP2ClientVirtualConnection *)((char *)this + 240),
              HTTP2ClientReceiveWindow);
      v51 = v50;
      if ( !v50 )
      {
        v19 = 14;
        goto LABEL_414;
      }
      v19 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v135 + 8LL))(
              v135,
              v50);
      if ( v19 )
        goto LABEL_414;
    }
    if ( v142 )
    {
      v19 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, __int64))(*(_QWORD *)v135 + 16LL))(v135, 1);
      if ( v19 )
        goto LABEL_430;
    }
    if ( v28 )
    {
      v19 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, __int64))(*(_QWORD *)v134 + 16LL))(v134, 4);
      if ( v19 )
        goto LABEL_430;
    }
    if ( v121 || v122 || v114 )
    {
      HTTP2ChannelPointer::UnlockChannelPointer(v139, v33);
      v137 = 0;
      v134 = 0;
    }
    if ( v123 || v126 || v115 )
    {
      HTTP2ChannelPointer::UnlockChannelPointer(v141, v33);
      v138 = 0;
      v135 = 0;
    }
    if ( v111 )
      goto LABEL_441;
    do
    {
      do
      {
        do
        {
          do
          {
            if ( WaitForSingleObject(hHandle, dwMilliseconds) == 258 )
            {
              v19 = 1818;
              v102 = 1390;
              v101 = dwMilliseconds;
              goto LABEL_457;
            }
          }
          while ( !v9 && *((_DWORD *)this + 104) == 997 && *((_DWORD *)this + 108) == 997 );
          v132 = v15;
          if ( a6 )
          {
            v118 = *((_DWORD *)this + 104);
            if ( v118 == -1073606617 )
            {
              if ( v128 )
              {
                v19 = -1073606617;
                v86 = HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(this, 0);
                (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v86);
                v88 = 1388;
                v89 = v15;
                goto LABEL_427;
              }
              v128 = HTTP2ClientVirtualConnection::GetInChannelChosenScheme(this, v9, 0);
              v116 = 0;
              v112 = 0;
              v114 = 0;
              *((_DWORD *)this + 104) = 997;
              v121 = 1;
              v122 = 1;
              v132 = 6;
              if ( !v15 )
                goto LABEL_206;
              if ( v15 == 2 )
              {
                v15 = 5;
LABEL_206:
                v144 = 1;
                goto LABEL_208;
              }
              v33 = v15 == 5;
              v144 = v15 == 5;
            }
          }
LABEL_208:
          v136 = v16;
          if ( !a7 )
            goto LABEL_292;
          v52 = *((_DWORD *)this + 108);
          v119 = v52;
          if ( v52 == -1073606617 )
          {
            if ( !v129 )
            {
              OutChannelChosenScheme = HTTP2ClientVirtualConnection::GetOutChannelChosenScheme(this, v9, 0);
              v129 = OutChannelChosenScheme;
              *((_DWORD *)this + 108) = 997;
              v117 = 0;
              v110 = 0;
              v123 = 1;
              v126 = 1;
              v115 = 0;
              v136 = 6;
              switch ( v16 )
              {
                case 0:
                  goto LABEL_214;
                case 4:
                  v115 = 1;
                  goto LABEL_214;
                case 2:
                  v16 = 5;
                  goto LABEL_214;
                case 5:
                  v144 = 1;
                  break;
                default:
LABEL_214:
                  v142 = 1;
                  break;
              }
              if ( a6 && v15 == 4 )
              {
                v33 = 0;
                v128 = OutChannelChosenScheme;
                v144 = 0;
                v116 = 1;
                v112 = 1;
                v121 = 0;
                v122 = 1;
                v118 = -1073606617;
                *((_DWORD *)this + 104) = 997;
                v132 = 6;
                v114 = 1;
              }
              goto LABEL_218;
            }
            v19 = -1073606617;
            v91 = HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(this, 0);
            (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v91);
            v88 = 1387;
            v89 = v16;
LABEL_427:
            v90 = -1073606617;
LABEL_428:
            v109 = v9;
            goto LABEL_429;
          }
LABEL_218:
          if ( v16 && v16 != 5 || v52 == -1073606617 )
          {
LABEL_292:
            v30 = v110;
            goto LABEL_293;
          }
          v19 = *((_DWORD *)this + 108);
          v119 = v19;
          if ( v16 )
          {
            if ( !v9 && v19 == 997 )
            {
              v30 = 0;
              v110 = 0;
              v117 = 0;
              v123 = 0;
              v126 = 0;
              v142 = 0;
              v115 = 0;
              goto LABEL_293;
            }
            if ( v19 && v19 != -1073606617 && v19 != -1073606612 )
              goto LABEL_433;
          }
          else
          {
            v54 = *((_DWORD *)this + 104);
            if ( !v54 )
              goto LABEL_292;
            if ( v54 == -1073606612 || v54 == -1073606617 )
              goto LABEL_233;
            Sleep(0x64u);
            v54 = *((_DWORD *)this + 104);
            if ( !v54 )
              goto LABEL_292;
            if ( v54 == -1073606612 || v54 == -1073606617 )
            {
LABEL_233:
              if ( v54 == -1073606612 || v54 == -1073606617 || v19 != -1073606612 )
                goto LABEL_292;
LABEL_236:
              v30 = v110;
              v119 = 5;
              goto LABEL_293;
            }
            if ( v19 && v19 != -1073606617 )
            {
              if ( v19 != -1073606612 )
                goto LABEL_292;
              v55 = *((_QWORD *)this + 76);
              if ( !v55 )
                goto LABEL_236;
              if ( (*(_BYTE *)(v55 + 8) & 2) != 0 )
                goto LABEL_233;
              v56 = *((_QWORD *)this + 76);
              if ( v56 )
              {
                if ( (*(_BYTE *)(v56 + 8) & 2) != 0 )
                {
                  v19 = 5;
                  v119 = 5;
LABEL_433:
                  v92 = HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(this, 0);
                  (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v92);
                  v90 = v119;
                  v88 = 1391;
                  v89 = v16;
                  goto LABEL_428;
                }
              }
            }
          }
          v57 = v120;
          if ( !v120 )
          {
            v57 = HTTP2ClientVirtualConnection::GetOutChannelChosenScheme(this, v9, 1);
            v120 = v57;
          }
          if ( v57 == 2 && *((_DWORD *)a2 + 8) == 2 )
          {
            v58 = *((_QWORD *)this + 76);
            if ( v58 )
            {
              if ( (*(_BYTE *)(v58 + 8) & 1) == 0 )
              {
LABEL_434:
                v19 = 1764;
                goto LABEL_430;
              }
            }
          }
          v59 = v16;
          v60 = v57 & 0x20000;
          if ( (v57 & 0x20000) != 0 )
          {
            if ( !v16 || v129 && (v61 = *((_QWORD *)this + 76)) != 0 && (*(_BYTE *)(v61 + 8) & 2) == 0 )
            {
              v123 = 0;
              v62 = 1;
              v117 = 1;
            }
            else
            {
              v62 = 0;
              v117 = 0;
              v123 = 1;
            }
            v27 = a8;
            v16 = 2;
            v126 = 1;
            v115 = 0;
            v142 = 1;
          }
          else
          {
            v63 = *((_QWORD *)this + 76);
            if ( v63 && (*(_BYTE *)(v63 + 8) & 1) != 0 )
            {
              IsKeepAlive = 1;
            }
            else
            {
              if ( a8 )
                v65 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * (*((_DWORD *)this + 68) ^ 1));
              else
                v65 = this;
              v66 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v65 + 200), v33);
              IsKeepAlive = HTTP2ClientOutChannel::IsKeepAlive(v66);
              HTTP2ChannelPointer::UnlockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v65 + 200), v67);
              v57 = v120;
            }
            v126 = 1;
            v27 = a8;
            v16 = v57 != 0 ? 4 : 1;
            v123 = IsKeepAlive != 0;
            v62 = IsKeepAlive == 0;
            v117 = v62;
            if ( a8 )
            {
              v142 = 0;
              v111 = 1;
            }
            else
            {
              v115 = 1;
              v142 = 1;
              v117 = IsKeepAlive == 0;
              v123 = IsKeepAlive != 0;
            }
          }
          v110 = v62;
          v30 = v62;
          *((_DWORD *)this + 108) = 997;
          if ( v15 )
          {
            v17 = v113;
            v31 = v112;
            v26 = a2;
          }
          else
          {
            v68 = v128;
            v31 = 1;
            v112 = 1;
            v116 = 1;
            v121 = 0;
            v122 = 1;
            if ( !v128 )
            {
              if ( v129 )
                v68 = v129;
              v128 = v68;
            }
            v17 = v113;
            if ( v113 )
            {
              v114 = (v113 & 0x20000) == 0;
              v15 = (v113 & 0x20000) != 0 ? 2 : 4;
            }
            else
            {
              v114 = 0;
              v15 = 5;
            }
            if ( v60 )
              v144 = 1;
            else
              v144 = v15 == 5;
            v26 = a2;
            v127 = 2;
            *((_DWORD *)a2 + 8) = 2;
          }
          if ( !(_DWORD)v27 )
          {
            v130 = 1;
            v131 = 3;
          }
          v28 = v144;
          v69 = v59 == 0;
          v9 = a8;
          if ( v69 || a8 )
            goto LABEL_90;
LABEL_293:
          v70 = a6;
          if ( !a6 || v15 && v15 != 5 )
            goto LABEL_357;
          v27 = v118;
          v33 = v124;
          if ( v118 != -1073606617 )
          {
            if ( v15 )
            {
              v71 = 2;
              if ( v9 )
                v71 = 3;
            }
            else
            {
              v71 = 1;
            }
            v27 = *((unsigned int *)this + 104);
            v118 = *((_DWORD *)this + 104);
            if ( v71 == 2 )
            {
              if ( (_DWORD)v27 == 997 )
              {
                v17 = v113;
                v27 = 0;
                v26 = a2;
                v28 = 0;
                v144 = 0;
                v112 = 0;
                v116 = 0;
                v121 = 0;
                v122 = 0;
                v114 = 0;
                goto LABEL_96;
              }
LABEL_303:
              if ( (_DWORD)v27 )
              {
LABEL_307:
                if ( (_DWORD)v27 != -1073606612 )
                  goto LABEL_308;
              }
            }
            else
            {
              if ( v71 == 3 )
                goto LABEL_303;
              if ( (_DWORD)v27 )
              {
                if ( (_DWORD)v27 != -1073606617 )
                {
                  if ( (_DWORD)v27 != -1073606612 )
                    goto LABEL_358;
                  v75 = *((_QWORD *)this + 76);
                  if ( !v75 || (*(_BYTE *)(v75 + 8) & 2) != 0 )
                  {
                    v27 = 5;
                    v118 = 5;
                    goto LABEL_358;
                  }
                }
                v72 = *((_QWORD *)this + 76);
                if ( !v72 || (*(_BYTE *)(v72 + 8) & 2) == 0 )
                  goto LABEL_307;
LABEL_308:
                if ( (_DWORD)v27 != -1073606617 )
                {
                  v19 = *((_DWORD *)this + 104);
                  if ( (_DWORD)v27 == -1073606612 )
                    v19 = 5;
                  v93 = HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(this, 0);
                  (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v93);
                  v88 = 1392;
                  v109 = v9;
                  v89 = v15;
                  goto LABEL_438;
                }
              }
            }
            v17 = v113;
            if ( !v113 )
            {
              v17 = HTTP2ClientVirtualConnection::GetInChannelChosenScheme(this, v9, 1);
              v113 = v17;
            }
            if ( v17 == 2 && *((_DWORD *)a2 + 8) == 2 )
            {
              v27 = *((_QWORD *)this + 76);
              if ( v27 )
              {
                if ( (*(_BYTE *)(v27 + 8) & 1) == 0 )
                  goto LABEL_434;
              }
            }
            v73 = v15;
            if ( (v17 & 0x20000) != 0 )
            {
              if ( !v15 || v128 && (v74 = *((_QWORD *)this + 76)) != 0 && (*(_BYTE *)(v74 + 8) & 2) == 0 )
              {
                v31 = 1;
                v116 = 1;
                v121 = 0;
              }
              else
              {
                v31 = 0;
                v121 = 1;
                v116 = 0;
              }
              v15 = 2;
              v122 = 1;
              v114 = 0;
              v144 = 1;
            }
            else
            {
              v76 = *((_QWORD *)this + 76);
              if ( v76 && (*(_BYTE *)(v76 + 8) & 1) != 0 )
              {
                v77 = 1;
              }
              else
              {
                if ( v9 )
                  v78 = (HTTP2ClientVirtualConnection *)((char *)this + 16 * (*((_DWORD *)this + 48) ^ 1));
                else
                  v78 = this;
                v79 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v78 + 120), v33);
                v77 = HTTP2ClientInChannel::IsKeepAlive(v79);
                HTTP2ChannelPointer::UnlockChannelPointer((HTTP2ClientVirtualConnection *)((char *)v78 + 120), v80);
              }
              v27 = -v113;
              v122 = 1;
              v15 = v113 != 0 ? 4 : 1;
              v121 = v77 != 0;
              v31 = v77 == 0;
              v116 = v31;
              if ( v9 )
                v111 = 1;
              else
                v114 = 1;
              v17 = v113;
              v144 = 0;
            }
            v112 = v31;
            *((_DWORD *)this + 104) = 997;
            if ( v16 )
            {
              v30 = v110;
              v26 = a2;
            }
            else
            {
              v27 = v129;
              v30 = 1;
              v110 = 1;
              v117 = 1;
              v123 = 0;
              v126 = 1;
              v142 = 1;
              if ( !v129 )
              {
                if ( v128 )
                  v27 = v128;
                v129 = v27;
              }
              if ( v120 )
              {
                v27 = (v120 & 0x20000) == 0;
                v115 = (v120 & 0x20000) == 0;
                v16 = (v120 & 0x20000) != 0 ? 2 : 4;
              }
              else
              {
                v115 = 0;
                v16 = 5;
              }
              v26 = a2;
              v127 = 1;
              *((_DWORD *)a2 + 8) = 1;
            }
            if ( !v9 )
            {
              v130 = 1;
              v131 = 3;
            }
            v69 = v73 == 0;
            v28 = v144;
            if ( v69 || v9 )
              goto LABEL_90;
            v70 = a6;
LABEL_357:
            v27 = v118;
          }
LABEL_358:
          if ( v9 )
            goto LABEL_364;
          if ( *((_DWORD *)this + 80) == 2 )
          {
            v51 = 0;
            v19 = HTTP_CopyResolverHint((HTTP2ClientVirtualConnection *)((char *)this + 448), a2, 0);
            if ( v19 )
              goto LABEL_414;
            *((_DWORD *)this + 156) = v128;
            *((_DWORD *)this + 157) = v129;
LABEL_441:
            RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
            if ( a6 )
            {
              if ( v9 && *((_DWORD *)this + 95) )
              {
                v95 = v139;
                v96 = HTTP2ChannelPointer::LockChannelPointer(v139, v94);
                if ( !v96 )
                {
                  v19 = -1073606638;
                  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
                  goto LABEL_430;
                }
                v19 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, bool, __int64))(*(_QWORD *)v96 + 112LL))(
                        v96,
                        *((_DWORD *)this + 95) != 0,
                        1);
                if ( v19 )
                {
                  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
                  v51 = 0;
                  v49 = 0;
                  goto LABEL_416;
                }
                HTTP2ChannelPointer::UnlockChannelPointer(v95, v106);
              }
              *((_QWORD *)this + 50) = 0;
            }
            if ( a7 )
              *((_QWORD *)this + 51) = 0;
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
            CloseHandle(hHandle);
            return 0;
          }
          if ( v15 == 5 )
          {
            v28 = v144;
            v17 = v113;
            v31 = v112;
            if ( (_DWORD)v27 != -1073606617 )
              goto LABEL_89;
          }
          if ( v16 == 5 )
          {
            v28 = v144;
            v17 = v113;
            v31 = v112;
            if ( v119 != -1073606617 )
              goto LABEL_89;
          }
LABEL_364:
          if ( v70 && v132 == 2 && (v19 = *((_DWORD *)this + 104), LODWORD(v27) = v19, v118 = v19, v19 != 997) )
          {
            if ( v19 && v19 != -1073606612 )
            {
              v97 = HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(this, 0);
              (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v97);
              v88 = 1393;
LABEL_447:
              v109 = v19;
              v89 = 2;
              goto LABEL_438;
            }
            v81 = v111;
            v31 = 0;
            v121 = 1;
            v122 = 1;
            *((_DWORD *)this + 104) = 997;
            if ( v9 )
              v81 = 1;
            v112 = 0;
            v116 = 0;
            v144 = 0;
            v111 = v81;
            v15 = 3;
            v114 = v9 == 0;
          }
          else
          {
            v81 = v111;
            v31 = v112;
          }
          v33 = a7;
          v82 = v136;
          if ( !a7 )
            goto LABEL_381;
          if ( v136 != 2 )
            goto LABEL_381;
          v19 = *((_DWORD *)this + 108);
          v119 = v19;
          if ( v19 == 997 )
            goto LABEL_381;
          if ( v19 && v19 != -1073606612 )
          {
            v98 = HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(this, 0);
            (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v98);
            v88 = 1394;
            goto LABEL_447;
          }
          v30 = 0;
          *((_DWORD *)this + 108) = 997;
          v110 = 0;
          v117 = 0;
          if ( v9 )
            v81 = 1;
          v123 = 1;
          v126 = 1;
          v111 = v81;
          v16 = 3;
          v115 = v9 == 0;
          v142 = v115;
          v70 = a6;
LABEL_381:
          if ( v9 || v15 )
            goto LABEL_393;
          if ( v119 != 997 )
            goto LABEL_388;
        }
        while ( (_DWORD)v27 == 997 );
        if ( v120 != 2 )
          break;
        v83 = *((_QWORD *)this + 76);
        if ( !v83 )
          break;
        if ( (*(_BYTE *)(v83 + 8) & 3) == 0 )
          goto LABEL_434;
LABEL_388:
        ;
      }
      while ( (_DWORD)v27 == 997 && v119 != -1073606617 );
      if ( (_DWORD)v27 == -1073606617 )
        goto LABEL_393;
    }
    while ( v119 == 997 );
    if ( v119 == -1073606617 )
    {
LABEL_393:
      v27 = *((unsigned int *)this + 104);
      v118 = *((_DWORD *)this + 104);
      if ( !v70 || ((v132 - 1) & 0xFFFFFFFC) != 0 || v132 == 2 || !(_DWORD)v27 || (_DWORD)v27 == 997 )
      {
        v19 = *((_DWORD *)this + 108);
        v119 = v19;
        if ( !a7 || ((v82 - 1) & 0xFFFFFFFC) != 0 || v82 == 2 || !v19 || v19 == 997 )
        {
          if ( v132 == v15 )
          {
            v31 = 0;
            v28 = 0;
            v112 = 0;
            v144 = 0;
            v116 = 0;
            v121 = 0;
            v122 = 0;
            v114 = 0;
          }
          else
          {
            v28 = v144;
          }
          v26 = a2;
          v69 = v82 == v16;
          v17 = v113;
          if ( v69 )
          {
            v30 = 0;
            v110 = 0;
            v117 = 0;
            v123 = 0;
            v126 = 0;
            v142 = 0;
            v115 = 0;
LABEL_89:
            v26 = a2;
            continue;
          }
          continue;
        }
        v104 = *((_DWORD *)this + 108);
        if ( v19 == -1073606612 )
          v19 = 5;
        v105 = HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(this, 0);
        (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v105);
        v88 = 1398;
        v109 = v104;
        v89 = v82;
      }
      else
      {
        v19 = *((_DWORD *)this + 104);
        if ( (_DWORD)v27 == -1073606612 )
          v19 = 5;
        v103 = HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(this, 0);
        (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v103);
        v88 = 1397;
        v109 = v118;
        v89 = v132;
      }
LABEL_438:
      v90 = v19;
LABEL_429:
      CompRpcpErrorAddRecord(v87, v90, v88, v89, v109);
      goto LABEL_430;
    }
    break;
  }
  if ( (_DWORD)v27 == 5 || v119 == 5 )
  {
    v19 = 5;
  }
  else
  {
    v19 = 1728;
    if ( (_DWORD)v27 != 1728 && v119 != 1728 || *((_DWORD *)a2 + 7) != 1 )
      v19 = 1722;
  }
  v99 = HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(this, 0);
  (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v99);
  CompRpcpErrorAddRecord(0xEu, v19, 0x573u, v118);
  v100 = HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(this, 0);
  (*((void (__fastcall **)(struct tagExtendedErrorInfo *))pRuntimeImportTable + 67))(v100);
  v101 = v119;
  v102 = 1396;
LABEL_457:
  CompRpcpErrorAddRecord(0xEu, v19, v102, v101);
LABEL_430:
  v51 = 0;
LABEL_414:
  v49 = 0;
LABEL_415:
  if ( v137 )
LABEL_416:
    HTTP2ChannelPointer::UnlockChannelPointer(v139, v33);
  if ( v138 )
    HTTP2ChannelPointer::UnlockChannelPointer(v141, v33);
  if ( v49 )
    (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v49);
  if ( v51 )
    (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v51);
LABEL_423:
  if ( ((v19 + 1073606648) & 0xFFFFFFF5) == 0 && v19 != -1073606640 )
  {
    v84 = 1399;
    v85 = v19;
    goto LABEL_478;
  }
  v85 = -1073606647;
  switch ( v19 )
  {
    case 0xC0021009:
      if ( v9 )
      {
        v84 = 1386;
LABEL_478:
        CompRpcpErrorAddRecord(0xEu, 0x6BAu, v84, v85);
        v19 = 1722;
      }
      break;
    case 0x718u:
    case 0xA4u:
      v19 = 14;
      break;
    case 0xC0021027:
      v19 = 1729;
      break;
  }
  if ( v133 )
    HTTP2ClientVirtualConnection::UnblockAborts(this);
  v10 = hHandle;
LABEL_487:
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
  if ( a6 )
    *((_QWORD *)this + 50) = 0;
  if ( a7 )
    *((_QWORD *)this + 51) = 0;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
  if ( v10 )
    CloseHandle(v10);
  if ( !a9 )
    (*(void (__fastcall **)(HTTP2ClientVirtualConnection *, _QWORD))(*(_QWORD *)this + 64LL))(this, 0);
  return v19;
}

```

## disassembly

```asm
0x180006050  mov     rax, rsp
0x180006053  mov     [rax+20h], rbx
0x180006057  mov     [rax+18h], r8d
0x18000605b  mov     [rax+10h], rdx
0x18000605f  push    rbp
0x180006060  push    rsi
0x180006061  push    rdi
0x180006062  push    r12
0x180006064  push    r13
0x180006066  push    r14
0x180006068  push    r15
0x18000606a  lea     rbp, [rax-48h]
0x18000606e  sub     rsp, 110h
0x180006075  mov     r15d, [rbp+40h+arg_38]
0x18000607c  xor     r14d, r14d
0x18000607f  mov     [rbp+40h+var_68], r14
0x180006083  mov     r8, rdx
0x180006086  mov     [rbp+40h+var_60], r14
0x18000608a  mov     rsi, rcx
0x18000608d  test    r15d, r15d
0x180006090  jnz     short loc_1800060C4
0x180006092  cmp     r9d, 0Ah
0x180006096  jz      short loc_1800060BA
0x180006098  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000609f  mov     ecx, r9d
0x1800060a2  mov     rax, [rax+98h]
0x1800060a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ae  mov     r8, [rbp+40h+arg_8]
0x1800060b2  mov     [rsi+178h], eax
0x1800060b8  jmp     short loc_1800060C4
0x1800060ba  mov     dword ptr [rcx+178h], 0FFFFFFFFh
0x1800060c4  mov     rcx, [rsi+260h]
0x1800060cb  mov     eax, 7
0x1800060d0  mov     ebx, [rbp+40h+arg_28]
0x1800060d3  mov     r12d, eax
0x1800060d6  mov     [rsp+140h+var_C4], r14d
0x1800060db  mov     r13d, eax
0x1800060de  mov     edi, r14d
0x1800060e1  mov     r9d, 20000h
0x1800060e7  lea     eax, [r12-6]
0x1800060ec  test    rcx, rcx
0x1800060ef  jz      short loc_18000616C
0x1800060f1  mov     rdx, [rcx+18h]
0x1800060f5  test    rdx, rdx
0x1800060f8  jz      short loc_180006144
0x1800060fa  test    byte ptr [rcx+8], 2
0x1800060fe  jnz     short loc_18000610C
0x180006100  mov     eax, [rdx]
0x180006102  sub     eax, r9d
0x180006105  test    eax, 0FFFDFFFFh
0x18000610a  jnz     short loc_18000613F
0x18000610c  mov     edi, [rdx]
0x18000610e  test    ebx, ebx
0x180006110  jz      short loc_180006124
0x180006112  mov     eax, edi
0x180006114  and     eax, r9d
0x180006117  neg     eax
0x180006119  sbb     r12d, r12d
0x18000611c  and     r12d, 0FFFFFFFEh
0x180006120  add     r12d, 4
0x180006124  cmp     [rbp+40h+arg_30], r14d
0x18000612b  jz      short loc_18000613F
0x18000612d  mov     eax, edi
0x18000612f  and     eax, r9d
0x180006132  neg     eax
0x180006134  sbb     r13d, r13d
0x180006137  and     r13d, 0FFFFFFFEh
0x18000613b  add     r13d, 4
0x18000613f  mov     eax, 1
0x180006144  cmp     edi, 2
0x180006147  jnz     short loc_18000615E
0x180006149  cmp     [r8+20h], edi
0x18000614d  jnz     short loc_18000615E
0x18000614f  test    [rcx+8], al
0x180006152  jnz     short loc_18000615E
0x180006154  mov     ebx, 6E4h
0x180006159  jmp     loc_180007B1D
0x18000615e  mov     [rbp+40h+var_A0], edi
0x180006161  mov     [rsp+140h+var_CC], r14d
0x180006166  mov     [rsp+140h+var_C4], edi
0x18000616a  jmp     short loc_180006180
0x18000616c  mov     [rbp+40h+var_A0], r14d
0x180006170  test    r15d, r15d
0x180006173  jnz     short loc_1800061B6
0x180006175  mov     [rsp+140h+var_CC], r14d
0x18000617a  mov     r12d, eax
0x18000617d  mov     r13d, eax
0x180006180  mov     eax, [rsi+270h]
0x180006186  xor     r9d, r9d; lpName
0x180006189  mov     [rbp+40h+var_80], eax
0x18000618c  xor     r8d, r8d; bInitialState
0x18000618f  mov     eax, [rsi+274h]
0x180006195  xor     edx, edx; bManualReset
0x180006197  xor     ecx, ecx; lpEventAttributes
0x180006199  mov     [rbp+40h+var_7C], eax
0x18000619c  call    cs:__imp_CreateEventW
0x1800061a2  mov     [rbp+40h+hHandle], rax
0x1800061a6  test    rax, rax
0x1800061a9  jnz     short loc_1800061C6
0x1800061ab  lea     ebx, [rax+0Eh]
0x1800061ae  mov     r14, rax
0x1800061b1  jmp     loc_180007B1D
0x1800061b6  mov     [rsp+140h+var_CC], eax
0x1800061ba  mov     r14d, eax
0x1800061bd  test    ebx, ebx
0x1800061bf  jz      short loc_18000617D
0x1800061c1  mov     r12d, eax
0x1800061c4  jmp     short loc_180006180
0x1800061c6  mov     [rbp+40h+var_6C], 0
0x1800061cd  test    r15d, r15d
0x1800061d0  jnz     short loc_18000621C
0x1800061d2  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800061d9  lea     rcx, [rsi+58h]
0x1800061dd  lea     edx, [r15+10h]
0x1800061e1  mov     rax, [rax+18h]
0x1800061e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ea  mov     ebx, eax
0x1800061ec  test    eax, eax
0x1800061ee  jnz     loc_1800076A5
0x1800061f4  cmp     [rbp+40h+arg_28], eax
0x1800061f7  jz      short loc_180006218
0x1800061f9  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180006200  lea     rcx, [rsi+0A0h]
0x180006207  lea     edx, [rbx+10h]
0x18000620a  mov     rax, [rax+18h]
0x18000620e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006213  mov     [rbp+40h+var_8C], ebx
0x180006216  jmp     short loc_18000624F
0x180006218  xor     eax, eax
0x18000621a  jmp     short loc_180006269
0x18000621c  test    ebx, ebx
0x18000621e  jz      short loc_180006260
0x180006220  mov     eax, [rsi+0C0h]
0x180006226  mov     edx, 10h
0x18000622b  xor     eax, 1
0x18000622e  movsxd  rcx, eax
0x180006231  mov     [rbp+40h+var_8C], eax
0x180006234  add     rcx, 0Ah
0x180006238  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000623f  shl     rcx, 4
0x180006243  add     rcx, rsi
0x180006246  mov     rax, [rax+18h]
0x18000624a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624f  mov     ebx, eax
0x180006251  xor     eax, eax
0x180006253  mov     [rbp+40h+var_90], eax
0x180006256  test    ebx, ebx
0x180006258  jnz     loc_1800076A5
0x18000625e  jmp     short loc_180006273
0x180006260  mov     eax, [rsi+110h]
0x180006266  xor     eax, 1
0x180006269  mov     [rbp+40h+var_90], eax
0x18000626c  mov     [rbp+40h+var_8C], 0
0x180006273  mov     edx, [rbp+40h+arg_30]
0x180006279  test    edx, edx
0x18000627b  jz      short loc_1800062BE
0x18000627d  mov     edx, 10h
0x180006282  test    r15d, r15d
0x180006285  jz      short loc_180006297
0x180006287  movsxd  rcx, eax
0x18000628a  add     rcx, 0Fh
0x18000628e  shl     rcx, 4
0x180006292  add     rcx, rsi
0x180006295  jmp     short loc_18000629E
0x180006297  lea     rcx, [rsi+0F0h]
0x18000629e  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800062a5  mov     rax, [rax+18h]
0x1800062a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ae  mov     ebx, eax
0x1800062b0  test    eax, eax
0x1800062b2  jnz     loc_1800076A5
0x1800062b8  mov     edx, [rbp+40h+arg_30]
0x1800062be  mov     r9d, [rbp+40h+arg_28]
0x1800062c2  xor     ecx, ecx
0x1800062c4  xor     eax, eax
0x1800062c6  mov     [rbp+40h+var_50], ecx
0x1800062c9  mov     [rbp+40h+var_54], eax
0x1800062cc  mov     r10d, 3E5h
0x1800062d2  mov     [rbp+40h+var_48], rax
0x1800062d6  mov     [rbp+40h+var_38], rax
0x1800062da  lea     r8d, [rcx+1]
0x1800062de  mov     [rbp+40h+var_74], eax
0x1800062e1  lea     eax, [rcx+57h]
0x1800062e4  mov     [rsp+78h], ecx
0x1800062e8  mov     rcx, [rbp+40h+hHandle]
0x1800062ec  mov     [rbp+40h+var_A8], eax
0x1800062ef  mov     [rbp+40h+var_A4], eax
0x1800062f2  test    r9d, r9d
0x1800062f5  jz      short loc_18000630B
0x1800062f7  mov     [rbp+40h+var_B0], r8d
0x1800062fb  mov     [rsi+1A0h], r10d
0x180006302  mov     [rsi+190h], rcx
0x180006309  jmp     short loc_180006310
0x18000630b  xor     eax, eax
0x18000630d  mov     [rbp+40h+var_B0], eax
0x180006310  test    edx, edx
0x180006312  jz      short loc_180006328
0x180006314  mov     [rbp+40h+var_AC], r8d
0x180006318  mov     [rsi+1B0h], r10d
0x18000631f  mov     [rsi+198h], rcx
0x180006326  jmp     short loc_18000632D
0x180006328  xor     eax, eax
0x18000632a  mov     [rbp+40h+var_AC], eax
0x18000632d  mov     rbx, [rbp+40h+arg_8]
0x180006331  mov     ecx, 5
0x180006336  mov     [rbp+40h+var_78], 0
0x18000633d  mov     eax, [rbx+20h]
0x180006340  mov     [rbp+40h+var_84], eax
0x180006343  test    eax, eax
0x180006345  jnz     short loc_180006395
0x180006347  xor     r12d, r12d
0x18000634a  xor     r13d, r13d
0x18000634d  mov     dword ptr [rsp+140h+var_110], r12d
0x180006352  xor     r9d, r9d
0x180006355  mov     dword ptr [rsp+140h+var_118], r8d
0x18000635a  mov     dl, 3Dh ; '='
0x18000635c  mov     r8, rsi
0x18000635f  mov     dword ptr [rsp+140h+var_120], 14h
0x180006367  mov     cl, 32h ; '2'
0x180006369  call    cs:__imp_I_RpcLogEvent
0x18000636f  lea     r10d, [r13+1]
0x180006373  mov     dword ptr [rsi+140h], 14h
0x18000637d  mov     r14d, r10d
0x180006380  mov     [rbp+40h+arg_10], r10d
0x180006384  mov     [rbp+40h+arg_0], r10d
0x180006388  mov     [rbp+40h+var_C0], r12d
0x18000638c  mov     [rbp+40h+var_BC], r12d
0x180006390  jmp     loc_1800064EA
0x180006395  test    edi, edi
0x180006397  jz      short loc_18000640E
0x180006399  bt      edi, 11h
0x18000639d  jnb     short loc_1800063C7
0x18000639f  mov     eax, r9d
0x1800063a2  neg     eax
0x1800063a4  mov     eax, edx
0x1800063a6  sbb     r12d, r12d
0x1800063a9  xor     ebx, ebx
0x1800063ab  and     r12d, 0FFFFFFFBh
0x1800063af  add     r12d, 7
0x1800063b3  test    edx, edx
0x1800063b5  setnz   bl
0x1800063b8  neg     eax
0x1800063ba  sbb     r13d, r13d
0x1800063bd  and     r13d, 0FFFFFFFBh
0x1800063c1  add     r13d, 7
0x1800063c5  jmp     short loc_180006405
0x1800063c7  test    r9d, r9d
0x1800063ca  jz      short loc_1800063E1
0x1800063cc  mov     r12d, 4
0x1800063d2  test    r15d, r15d
0x1800063d5  jz      short loc_1800063E7
0x1800063d7  mov     r14d, r8d
0x1800063da  mov     [rsp+140h+var_CC], r8d
0x1800063df  jmp     short loc_1800063E7
0x1800063e1  mov     r12d, 7
0x1800063e7  test    edx, edx
0x1800063e9  jz      short loc_180006449
0x1800063eb  test    r15d, r15d
0x1800063ee  mov     r13d, 4
0x1800063f4  cmovnz  r14d, r8d
0x1800063f8  xor     ebx, ebx
0x1800063fa  test    r15d, r15d
0x1800063fd  mov     [rsp+140h+var_CC], r14d
0x180006402  setz    bl
0x180006405  mov     [rbp+40h+arg_0], ebx
0x180006408  mov     rbx, [rbp+40h+arg_8]
0x18000640c  jmp     short loc_180006456
0x18000640e  test    r9d, r9d
0x180006411  jz      short loc_18000641D
0x180006413  cmp     r12d, r8d
0x180006416  jz      short loc_180006423
0x180006418  mov     r12d, ecx
0x18000641b  jmp     short loc_180006423
0x18000641d  mov     r12d, 7
0x180006423  test    edx, edx
0x180006425  jz      short loc_180006449
0x180006427  cmp     r13d, r8d
0x18000642a  jz      short loc_180006435
0x18000642c  mov     r13d, ecx
0x18000642f  mov     [rbp+40h+arg_0], r8d
0x180006433  jmp     short loc_180006456
0x180006435  test    r15d, r15d
0x180006438  jz      short loc_180006443
0x18000643a  mov     [rbp+40h+arg_0], 0
0x180006441  jmp     short loc_18000648E
0x180006443  mov     [rbp+40h+arg_0], r8d
0x180006447  jmp     short loc_18000645B
0x180006449  mov     [rbp+40h+arg_0], 0
0x180006450  mov     r13d, 7
0x180006456  test    r15d, r15d
0x180006459  jnz     short loc_18000648E
0x18000645b  mov     dword ptr [rsp+140h+var_110], 0
0x180006463  xor     r9d, r9d
0x180006466  mov     dword ptr [rsp+140h+var_118], r8d
0x18000646b  mov     dl, 3Dh ; '='
0x18000646d  mov     r8, rsi
0x180006470  mov     dword ptr [rsp+140h+var_120], 3
0x180006478  mov     cl, 32h ; '2'
0x18000647a  call    cs:__imp_I_RpcLogEvent
0x180006480  mov     r9d, [rbp+40h+arg_28]
  ... truncated ...
```
