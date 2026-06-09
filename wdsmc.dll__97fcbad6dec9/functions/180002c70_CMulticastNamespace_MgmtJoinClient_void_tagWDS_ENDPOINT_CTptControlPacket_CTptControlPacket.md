# CMulticastNamespace::MgmtJoinClient(void *,tagWDS_ENDPOINT *,CTptControlPacket *,CTptControlPacket *)

- ea: `0x180002c70`
- end: `0x1800031de`
- name: `?MgmtJoinClient@CMulticastNamespace@@QEAAKPEAXPEAUtagWDS_ENDPOINT@@PEAVCTptControlPacket@@2@Z`
- size: `1390`
- prototype: `unsigned int __usercall@<eax>(CMulticastNamespace *__hidden this@<rcx>, void *@<rdx>, struct tagWDS_ENDPOINT *@<r8>, struct CTptControlPacket *@<r9>, struct CTptControlPacket *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, service_task`

## callers

- `0x1800070ac`

## callees

- `0x1800021f4`
- `0x180002c70`
- `0x180003590`
- `0x180003b08`
- `0x180003e18`
- `0x180003f10`
- `0x180004184`
- `0x18000433c`
- `0x180004530`
- `0x180004be0`
- `0x180004c60`
- `0x18000b178`
- `0x18000b290`
- `0x18000b430`
- `0x18001a9a8`
- `0x1800209c8`
- `0x180020bd0`
- `0x180025850`
- `0x180026670`
- `0x1800266a0`
- `0x180026d46`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800031b6`
- `KERNEL32!LeaveCriticalSection` at `0x1800031b6`
- `KERNEL32!EnterCriticalSection` at `0x180002ce1`
- `KERNEL32!EnterCriticalSection` at `0x180002ce1`
- `KERNEL32!DeleteCriticalSection` at `0x180003189`
- `KERNEL32!DeleteCriticalSection` at `0x180003189`

## string_xrefs

- `0x180002e46`: `WDSMCNS[%u:%s] Provider does not service unauthenticated requests.`
- `0x180002eee`: `WDSMCNS[%u:%s] Client=`%s' Rejecting request because scheduled namespace has already started and no new clients are allowed.`

## pseudocode

```c
__int64 __fastcall CMulticastNamespace::MgmtJoinClient(
        CMulticastNamespace *this,
        void *a2,
        struct tagWDS_ENDPOINT *a3,
        struct CTptControlPacket *a4,
        struct CTptControlPacket *a5)
{
  int v8; // r13d
  CMulticastContent *v9; // rsi
  unsigned int String; // edi
  const char *v11; // rdx
  unsigned int v12; // eax
  const struct reg_FeatureDescriptor *v13; // rcx
  unsigned __int16 *v14; // r15
  unsigned int ULONG; // eax
  const char *v16; // rdx
  unsigned int v17; // r9d
  unsigned int v18; // r14d
  const char *v19; // rdx
  __int64 v20; // rdx
  int v21; // ecx
  const char *v22; // rdx
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rdi
  struct _RTL_CRITICAL_SECTION *v24; // r14
  const char *v25; // rdx
  CMulticastContent *v26; // rax
  const char *v27; // rdx
  const char *v28; // rdx
  _QWORD *v29; // rax
  _QWORD *v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // r11
  struct CTptControlPacket *v34; // [rsp+28h] [rbp-89h]
  unsigned __int16 *v35; // [rsp+40h] [rbp-71h] BYREF
  int v36; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 *v37; // [rsp+50h] [rbp-61h] BYREF
  void *v38; // [rsp+58h] [rbp-59h] BYREF
  struct CTptControlPacket *v39; // [rsp+60h] [rbp-51h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-49h]
  unsigned int v41[2]; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+78h] [rbp-39h]
  _BYTE v43[48]; // [rsp+80h] [rbp-31h] BYREF

  v38 = a2;
  v39 = a5;
  v35 = 0;
  v37 = 0;
  v8 = 0;
  memset_0(v43, 0, sizeof(v43));
  v36 = 0;
  *(_QWORD *)v41 = 0;
  v9 = 0;
  v42 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 30) )
  {
    String = -1054801656;
    goto LABEL_69;
  }
  String = CControlPacket::GetString(a4, L"Client", 0, 0xFFFFFFFF, &v35);
  v12 = ElValidateWin32(String, v11, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x290u);
  v14 = v35;
  if ( v12 )
    goto LABEL_52;
  String = CControlPacket::GetString(a4, L"Content", 0, 0xFFFFFFFF, &v37);
  if ( !String )
  {
    ULONG = CControlPacket::GetULONG(a4, L"Cap", 0, 0xFFFFFFFF, &v41[1]);
    String = ULONG;
    if ( (ULONG & 0xFFFFFFFD) != 0 )
    {
      v17 = 680;
LABEL_51:
      ElValidateWin32(ULONG, v16, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", v17);
      goto LABEL_52;
    }
    v18 = (v41[1] >> 2) & 1;
    v42 = v18;
    String = CMulticastNamespace::GetLocalInterface(
               this,
               a3,
               (struct _WDSMC_SESSION_PARAMETERS *)v41,
               (struct tagWDS_INTERFACE_INFO *)v43);
    if ( ElValidateWin32(String, v19, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x2B5u) )
    {
      if ( String == 2 )
        String = -1054735604;
      goto LABEL_52;
    }
    if ( v18 )
    {
      v41[0] = 196611;
    }
    else
    {
      v21 = *((_DWORD *)this + 59);
      v20 = 3;
      if ( ((unsigned __int16)v21 == 3 || HIWORD(v21) == 3) && (v41[1] & 1) == 0 )
      {
        String = -1054801648;
        goto LABEL_65;
      }
      v41[0] = *((_DWORD *)this + 59);
    }
    if ( v18 == 1 && !*(_DWORD *)(*((_QWORD *)this + 22) + 52LL) )
    {
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(
          L"WDSMCNS[%u:%s] Provider does not service unauthenticated requests.",
          *((unsigned int *)this + 14),
          *((_QWORD *)this + 10));
      String = 5;
      goto LABEL_65;
    }
    if ( g_ErrLibTraceFunction )
    {
      LODWORD(v34) = v18;
      g_ErrLibTraceFunction(
        L"WDSMCNS[%u:%s] Join Request - Client='%s', Content=`%s', Boot=%u",
        *((unsigned int *)this + 14),
        *((_QWORD *)this + 10),
        v14,
        v37);
    }
    if ( *((_DWORD *)this + 18) == 2 && *((_DWORD *)this + 35) )
    {
      LODWORD(v35) = 0;
      String = CMcNsClients::AllowClient((LPCRITICAL_SECTION)this + 9, v14, (int *)&v35);
      if ( ElValidateWin32(String, v22, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x2F6u) )
        goto LABEL_52;
      if ( !(_DWORD)v35 )
      {
        if ( g_ErrLibTraceFunction )
          g_ErrLibTraceFunction(
            L"WDSMCNS[%u:%s] Client=`%s' Rejecting request because scheduled namespace has already started and no new clie"
             "nts are allowed.",
            *((unsigned int *)this + 14),
            *((_QWORD *)this + 10),
            v14);
        String = -1054801655;
        goto LABEL_65;
      }
    }
    DebugInfo = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 53);
    if ( DebugInfo )
    {
      do
      {
        v24 = DebugInfo;
        DebugInfo = (struct _RTL_CRITICAL_SECTION *)DebugInfo[77].DebugInfo;
        if ( !CMulticastContent::MatchContent(v24, (struct tagWDS_INTERFACE_INFO *)v20, v37, &v36) && v36 )
          break;
        v24 = 0;
      }
      while ( DebugInfo );
      if ( v24 )
      {
        String = CMulticastContent::MgmtJoinClient(
                   v24,
                   v38,
                   v14,
                   (struct _WDSMC_SESSION_PARAMETERS *)v41,
                   (struct tagWDS_INTERFACE_INFO *)v43,
                   v34,
                   v39);
        if ( ElValidateWin32(String, v25, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x31Eu) )
          goto LABEL_52;
LABEL_49:
        if ( *((_DWORD *)this + 18) == 2 )
        {
          ULONG = CMcNsClients::AddClient((LPCRITICAL_SECTION)this + 9, v14);
          String = ULONG;
          v17 = 841;
          goto LABEL_51;
        }
LABEL_52:
        if ( String && v9 )
        {
          if ( (unsigned int)EvaluateCurrentState(v13) && v8 )
          {
            v29 = (_QWORD *)*((_QWORD *)this + 53);
            if ( !v29 )
              goto LABEL_62;
            v38 = (void *)*((_QWORD *)this + 53);
            v30 = v29;
            v31 = (unsigned __int64)v29;
            while ( (CMulticastContent *)(v31 & -(__int64)(v30 != 0)) != v9 )
            {
              v29 = (_QWORD *)v29[385];
              v38 = v29;
              v30 = v29;
              v31 = (unsigned __int64)v29;
              if ( !v29 )
                goto LABEL_62;
            }
            CList<CMulticastContent,CNoLock>::DeleteAt((char *)this + 424, &v38);
            if ( !v32 )
            {
LABEL_62:
              if ( g_ErrLibTraceFunction )
                g_ErrLibTraceFunction(
                  L"WDSMCNS[%u:%s] Multicast content removal failed.",
                  *((unsigned int *)this + 14),
                  *((_QWORD *)this + 10));
            }
          }
          CMulticastContent::Close((LPCRITICAL_SECTION)v9, 1);
          CMulticastContent::Shutdown((LPCRITICAL_SECTION)v9);
          CMulticastContent::Shutdown((LPCRITICAL_SECTION)v9);
          CMcCoClients::Shutdown((CMulticastContent *)((char *)v9 + 312));
          DeleteCriticalSection((LPCRITICAL_SECTION)v9);
          operator delete(v9);
        }
        goto LABEL_65;
      }
    }
    v26 = (CMulticastContent *)operator new(0xC18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v26 )
      v9 = CMulticastContent::CMulticastContent(v26);
    if ( v9 )
    {
      String = CMulticastContent::Initialize(
                 (LPCRITICAL_SECTION)v9,
                 this,
                 *((struct CContentProvider **)this + 22),
                 v37);
      if ( ElValidateWin32(String, v27, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x32Bu) )
        goto LABEL_52;
      String = CMulticastContent::MgmtJoinClient(
                 (LPCRITICAL_SECTION)v9,
                 v38,
                 v14,
                 (struct _WDSMC_SESSION_PARAMETERS *)v41,
                 (struct tagWDS_INTERFACE_INFO *)v43,
                 v34,
                 v39);
      if ( ElValidateWin32(String, v28, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x335u) )
        goto LABEL_52;
      if ( *((_QWORD *)this + 53) )
      {
        *((_QWORD *)v9 + 385) = 0;
        *((_QWORD *)v9 + 386) = *((_QWORD *)this + 54);
        *(_QWORD *)(*((_QWORD *)this + 54) + 3080LL) = v9;
        *((_QWORD *)this + 54) = v9;
      }
      else
      {
        *((_QWORD *)this + 54) = v9;
        *((_QWORD *)this + 53) = v9;
        *((_QWORD *)v9 + 385) = 0;
        *((_QWORD *)v9 + 386) = 0;
      }
      ++*((_DWORD *)this + 111);
      v8 = 1;
      if ( *((_DWORD *)this + 35) )
        CMulticastContent::MgmtStart(v9);
      goto LABEL_49;
    }
    String = 8;
  }
LABEL_65:
  if ( v14 )
    operator delete(v14);
  if ( v37 )
    operator delete(v37);
LABEL_69:
  LeaveCriticalSection(lpCriticalSection);
  return String;
}

```

## disassembly

```asm
0x180002c70  push    rbp
0x180002c72  push    rbx
0x180002c73  push    rsi
0x180002c74  push    rdi
0x180002c75  push    r12
0x180002c77  push    r13
0x180002c79  push    r14
0x180002c7b  push    r15
0x180002c7d  lea     rbp, [rsp-17h]
0x180002c82  sub     rsp, 0C8h
0x180002c89  mov     rax, cs:__security_cookie
0x180002c90  xor     rax, rsp
0x180002c93  mov     [rbp+4Fh+var_50], rax
0x180002c97  mov     rax, [rbp+4Fh+arg_20]
0x180002c9b  xor     edi, edi
0x180002c9d  mov     r12, r8
0x180002ca0  mov     [rbp+4Fh+var_A8], rdx
0x180002ca4  mov     rbx, rcx
0x180002ca7  mov     [rbp+4Fh+var_A0], rax
0x180002cab  xor     edx, edx; Val
0x180002cad  mov     [rbp+4Fh+var_C0], rdi
0x180002cb1  lea     r8d, [rdi+30h]; Size
0x180002cb5  mov     [rbp+4Fh+var_B0], rdi
0x180002cb9  lea     rcx, [rbp+4Fh+var_80]; void *
0x180002cbd  mov     r14, r9
0x180002cc0  mov     r13d, edi
0x180002cc3  call    memset_0
0x180002cc8  xor     eax, eax
0x180002cca  mov     [rbp+4Fh+var_B8], edi
0x180002ccd  mov     qword ptr [rbp+4Fh+var_90], rax
0x180002cd1  mov     esi, edi
0x180002cd3  mov     [rbp+4Fh+var_88], eax
0x180002cd6  lea     rax, [rbx+10h]
0x180002cda  mov     rcx, rax; lpCriticalSection
0x180002cdd  mov     [rbp+4Fh+lpCriticalSection], rax
0x180002ce1  call    cs:__imp_EnterCriticalSection
0x180002ce7  cmp     [rbx+78h], edi
0x180002cea  jz      short loc_180002CF6
0x180002cec  mov     edi, 0C1210108h
0x180002cf1  jmp     loc_1800031B2
0x180002cf6  lea     rax, [rbp+4Fh+var_C0]
0x180002cfa  or      r9d, 0FFFFFFFFh; unsigned int
0x180002cfe  xor     r8d, r8d; unsigned __int16 *
0x180002d01  mov     [rsp+100h+var_E0], rax; unsigned __int16 **
0x180002d06  lea     rdx, aClient; "Client"
0x180002d0d  mov     rcx, r14; this
0x180002d10  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180002d15  mov     r9d, 290h; unsigned int
0x180002d1b  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002d22  mov     ecx, eax; unsigned int
0x180002d24  mov     edi, eax
0x180002d26  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002d2b  mov     r15, [rbp+4Fh+var_C0]
0x180002d2f  test    eax, eax
0x180002d31  jnz     loc_1800030CE
0x180002d37  lea     rax, [rbp+4Fh+var_B0]
0x180002d3b  or      r9d, 0FFFFFFFFh; unsigned int
0x180002d3f  xor     r8d, r8d; unsigned __int16 *
0x180002d42  mov     [rsp+100h+var_E0], rax; unsigned __int16 **
0x180002d47  lea     rdx, aContent; "Content"
0x180002d4e  mov     rcx, r14; this
0x180002d51  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180002d56  mov     edi, eax
0x180002d58  test    eax, eax
0x180002d5a  jnz     loc_180003197
0x180002d60  lea     rax, [rbp+4Fh+var_90+4]
0x180002d64  or      r9d, 0FFFFFFFFh; unsigned int
0x180002d68  xor     r8d, r8d; unsigned __int16 *
0x180002d6b  mov     [rsp+100h+var_E0], rax; unsigned int *
0x180002d70  lea     rdx, aCap; "Cap"
0x180002d77  mov     rcx, r14; this
0x180002d7a  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180002d7f  mov     edi, eax
0x180002d81  test    eax, 0FFFFFFFDh
0x180002d86  jz      short loc_180002D93
0x180002d88  mov     r9d, 2A8h
0x180002d8e  jmp     loc_1800030C0
0x180002d93  mov     r14d, [rbp+4Fh+var_90+4]
0x180002d97  lea     r9, [rbp+4Fh+var_80]; struct tagWDS_INTERFACE_INFO *
0x180002d9b  shr     r14d, 2
0x180002d9f  lea     r8, [rbp+4Fh+var_90]; struct _WDSMC_SESSION_PARAMETERS *
0x180002da3  and     r14d, 1
0x180002da7  mov     rdx, r12; struct tagWDS_ENDPOINT *
0x180002daa  mov     rcx, rbx; this
0x180002dad  mov     [rbp+4Fh+var_88], r14d
0x180002db1  call    ?GetLocalInterface@CMulticastNamespace@@AEAAKPEAUtagWDS_ENDPOINT@@PEAU_WDSMC_SESSION_PARAMETERS@@PEAUtagWDS_INTERFACE_INFO@@@Z; CMulticastNamespace::GetLocalInterface(tagWDS_ENDPOINT *,_WDSMC_SESSION_PARAMETERS *,tagWDS_INTERFACE_INFO *)
0x180002db6  mov     r9d, 2B5h; unsigned int
0x180002dbc  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002dc3  mov     ecx, eax; unsigned int
0x180002dc5  mov     edi, eax
0x180002dc7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002dcc  xor     r12d, r12d
0x180002dcf  test    eax, eax
0x180002dd1  jz      short loc_180002DE6
0x180002dd3  cmp     edi, 2
0x180002dd6  jnz     loc_1800030CE
0x180002ddc  mov     edi, 0C122030Ch
0x180002de1  jmp     loc_1800030CE
0x180002de6  test    r14d, r14d
0x180002de9  jz      short loc_180002DF4
0x180002deb  mov     [rbp+4Fh+var_90], 30003h
0x180002df2  jmp     short loc_180002E23
0x180002df4  mov     ecx, [rbx+0ECh]
0x180002dfa  mov     edx, 3
0x180002dff  movzx   eax, cx
0x180002e02  cmp     eax, edx
0x180002e04  jz      short loc_180002E10
0x180002e06  mov     eax, ecx
0x180002e08  shr     eax, 10h
0x180002e0b  cmp     ax, dx
0x180002e0e  jnz     short loc_180002E20
0x180002e10  test    byte ptr [rbp+4Fh+var_90+4], 1
0x180002e14  jnz     short loc_180002E20
0x180002e16  mov     edi, 0C1210110h
0x180002e1b  jmp     loc_180003197
0x180002e20  mov     [rbp+4Fh+var_90], ecx
0x180002e23  cmp     r14d, 1
0x180002e27  jnz     short loc_180002E60
0x180002e29  mov     rax, [rbx+0B0h]
0x180002e30  cmp     [rax+34h], r12d
0x180002e34  jnz     short loc_180002E60
0x180002e36  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180002e3d  test    rax, rax
0x180002e40  jz      short loc_180002E56
0x180002e42  mov     r8, [rbx+50h]
0x180002e46  lea     rcx, aWdsmcnsUSProvi; "WDSMCNS[%u:%s] Provider does not servic"...
0x180002e4d  mov     edx, [rbx+38h]
0x180002e50  call    cs:__guard_dispatch_icall_fptr
0x180002e56  mov     edi, 5
0x180002e5b  jmp     loc_180003197
0x180002e60  mov     r10, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180002e67  test    r10, r10
0x180002e6a  jz      short loc_180002E94
0x180002e6c  mov     rax, [rbp+4Fh+var_B0]
0x180002e70  lea     rcx, aWdsmcnsUSJoinR; "WDSMCNS[%u:%s] Join Request - Client='%"...
0x180002e77  mov     r8, [rbx+50h]
0x180002e7b  mov     r9, r15
0x180002e7e  mov     edx, [rbx+38h]
0x180002e81  mov     dword ptr [rsp+100h+var_D8], r14d; struct CTptControlPacket *
0x180002e86  mov     [rsp+100h+var_E0], rax
0x180002e8b  mov     rax, r10
0x180002e8e  call    cs:__guard_dispatch_icall_fptr
0x180002e94  cmp     dword ptr [rbx+48h], 2
0x180002e98  jnz     short loc_180002F0B
0x180002e9a  cmp     [rbx+8Ch], r12d
0x180002ea1  jz      short loc_180002F0B
0x180002ea3  lea     rcx, [rbx+168h]; lpCriticalSection
0x180002eaa  mov     dword ptr [rbp+4Fh+var_C0], r12d
0x180002eae  lea     r8, [rbp+4Fh+var_C0]; int *
0x180002eb2  mov     rdx, r15; unsigned __int16 *
0x180002eb5  call    ?AllowClient@CMcNsClients@@QEAAKPEBGPEAH@Z; CMcNsClients::AllowClient(ushort const *,int *)
0x180002eba  mov     r9d, 2F6h; unsigned int
0x180002ec0  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002ec7  mov     ecx, eax; unsigned int
0x180002ec9  mov     edi, eax
0x180002ecb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002ed0  test    eax, eax
0x180002ed2  jnz     loc_1800030CE
0x180002ed8  cmp     dword ptr [rbp+4Fh+var_C0], r12d
0x180002edc  jnz     short loc_180002F0B
0x180002ede  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180002ee5  test    rax, rax
0x180002ee8  jz      short loc_180002F01
0x180002eea  mov     r8, [rbx+50h]
0x180002eee  lea     rcx, aWdsmcnsUSClien; "WDSMCNS[%u:%s] Client=`%s' Rejecting re"...
0x180002ef5  mov     edx, [rbx+38h]
0x180002ef8  mov     r9, r15
0x180002efb  call    cs:__guard_dispatch_icall_fptr
0x180002f01  mov     edi, 0C1210109h
0x180002f06  jmp     loc_180003197
0x180002f0b  mov     rdi, [rbx+1A8h]
0x180002f12  test    rdi, rdi
0x180002f15  jz      short loc_180002F90
0x180002f17  mov     r8, [rbp+4Fh+var_B0]; unsigned __int16 *
0x180002f1b  lea     r9, [rbp+4Fh+var_B8]; int *
0x180002f1f  mov     r14, rdi
0x180002f22  mov     rdi, [rdi+0C08h]
0x180002f29  mov     rcx, r14; lpCriticalSection
0x180002f2c  call    ?MatchContent@CMulticastContent@@QEAAKPEAUtagWDS_INTERFACE_INFO@@PEBGPEAH@Z; CMulticastContent::MatchContent(tagWDS_INTERFACE_INFO *,ushort const *,int *)
0x180002f31  test    eax, eax
0x180002f33  jnz     short loc_180002F3B
0x180002f35  cmp     [rbp+4Fh+var_B8], r12d
0x180002f39  jnz     short loc_180002F43
0x180002f3b  mov     r14, r12
0x180002f3e  test    rdi, rdi
0x180002f41  jnz     short loc_180002F17
0x180002f43  test    r14, r14
0x180002f46  jz      short loc_180002F90
0x180002f48  mov     rax, [rbp+4Fh+var_A0]
0x180002f4c  lea     r9, [rbp+4Fh+var_90]; struct _WDSMC_SESSION_PARAMETERS *
0x180002f50  mov     rdx, [rbp+4Fh+var_A8]; void *
0x180002f54  mov     r8, r15; unsigned __int16 *
0x180002f57  mov     [rsp+100h+var_D0], rax; struct CTptControlPacket *
0x180002f5c  mov     rcx, r14; lpCriticalSection
0x180002f5f  lea     rax, [rbp+4Fh+var_80]
0x180002f63  mov     [rsp+100h+var_E0], rax; Buf1
0x180002f68  call    ?MgmtJoinClient@CMulticastContent@@QEAAKPEAXPEBGPEAU_WDSMC_SESSION_PARAMETERS@@PEAUtagWDS_INTERFACE_INFO@@PEAVCTptControlPacket@@4@Z; CMulticastContent::MgmtJoinClient(void *,ushort const *,_WDSMC_SESSION_PARAMETERS *,tagWDS_INTERFACE_INFO *,CTptControlPacket *,CTptControlPacket *)
0x180002f6d  mov     r9d, 31Eh; unsigned int
0x180002f73  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002f7a  mov     ecx, eax; unsigned int
0x180002f7c  mov     edi, eax
0x180002f7e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002f83  test    eax, eax
0x180002f85  jnz     loc_1800030CE
0x180002f8b  jmp     loc_1800030A3
0x180002f90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002f97  mov     ecx, 0C18h; unsigned __int64
0x180002f9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002fa1  test    rax, rax
0x180002fa4  jz      short loc_180002FB1
0x180002fa6  mov     rcx, rax; this
0x180002fa9  call    ??0CMulticastContent@@QEAA@XZ; CMulticastContent::CMulticastContent(void)
0x180002fae  mov     rsi, rax
0x180002fb1  test    rsi, rsi
0x180002fb4  jnz     short loc_180002FBE
0x180002fb6  lea     edi, [rsi+8]
0x180002fb9  jmp     loc_180003197
0x180002fbe  mov     r9, [rbp+4Fh+var_B0]; unsigned __int16 *
0x180002fc2  mov     rdx, rbx; struct CMulticastNamespace *
0x180002fc5  mov     r8, [rbx+0B0h]; struct CContentProvider *
0x180002fcc  mov     rcx, rsi; lpCriticalSection
0x180002fcf  call    ?Initialize@CMulticastContent@@QEAAKPEAVCMulticastNamespace@@PEAVCContentProvider@@PEBG@Z; CMulticastContent::Initialize(CMulticastNamespace *,CContentProvider *,ushort const *)
0x180002fd4  mov     r9d, 32Bh; unsigned int
0x180002fda  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002fe1  mov     ecx, eax; unsigned int
0x180002fe3  mov     edi, eax
0x180002fe5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002fea  test    eax, eax
0x180002fec  jnz     loc_1800030CE
0x180002ff2  mov     rax, [rbp+4Fh+var_A0]
0x180002ff6  lea     r9, [rbp+4Fh+var_90]; struct _WDSMC_SESSION_PARAMETERS *
0x180002ffa  mov     rdx, [rbp+4Fh+var_A8]; void *
0x180002ffe  mov     r8, r15; unsigned __int16 *
0x180003001  mov     [rsp+100h+var_D0], rax; struct CTptControlPacket *
0x180003006  mov     rcx, rsi; lpCriticalSection
0x180003009  lea     rax, [rbp+4Fh+var_80]
0x18000300d  mov     [rsp+100h+var_E0], rax; Buf1
0x180003012  call    ?MgmtJoinClient@CMulticastContent@@QEAAKPEAXPEBGPEAU_WDSMC_SESSION_PARAMETERS@@PEAUtagWDS_INTERFACE_INFO@@PEAVCTptControlPacket@@4@Z; CMulticastContent::MgmtJoinClient(void *,ushort const *,_WDSMC_SESSION_PARAMETERS *,tagWDS_INTERFACE_INFO *,CTptControlPacket *,CTptControlPacket *)
0x180003017  mov     r9d, 335h; unsigned int
0x18000301d  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180003024  mov     ecx, eax; unsigned int
0x180003026  mov     edi, eax
0x180003028  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000302d  test    eax, eax
0x18000302f  jnz     loc_1800030CE
0x180003035  cmp     [rbx+1A8h], r12
0x18000303c  jnz     short loc_18000305C
0x18000303e  mov     [rbx+1B0h], rsi
0x180003045  mov     [rbx+1A8h], rsi
0x18000304c  mov     [rsi+0C08h], r12
0x180003053  mov     [rsi+0C10h], r12
0x18000305a  jmp     short loc_180003086
0x18000305c  mov     [rsi+0C08h], r12
0x180003063  mov     rax, [rbx+1B0h]
0x18000306a  mov     [rsi+0C10h], rax
0x180003071  mov     rax, [rbx+1B0h]
0x180003078  mov     [rax+0C08h], rsi
0x18000307f  mov     [rbx+1B0h], rsi
0x180003086  inc     dword ptr [rbx+1BCh]
0x18000308c  mov     r13d, 1
0x180003092  cmp     [rbx+8Ch], r12d
0x180003099  jz      short loc_1800030A3
0x18000309b  mov     rcx, rsi; this
0x18000309e  call    ?MgmtStart@CMulticastContent@@QEAAXXZ; CMulticastContent::MgmtStart(void)
0x1800030a3  cmp     dword ptr [rbx+48h], 2
0x1800030a7  jnz     short loc_1800030CE
0x1800030a9  lea     rcx, [rbx+168h]; lpCriticalSection
0x1800030b0  mov     rdx, r15; unsigned __int16 *
0x1800030b3  call    ?AddClient@CMcNsClients@@QEAAKPEBG@Z; CMcNsClients::AddClient(ushort const *)
0x1800030b8  mov     edi, eax
0x1800030ba  mov     r9d, 349h; unsigned int
0x1800030c0  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800030c7  mov     ecx, eax; unsigned int
0x1800030c9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800030ce  test    edi, edi
0x1800030d0  jz      loc_180003197
0x1800030d6  test    rsi, rsi
0x1800030d9  jz      loc_180003197
0x1800030df  call    ?EvaluateCurrentState@@YAHPEBUreg_FeatureDescriptor@@@Z; EvaluateCurrentState(reg_FeatureDescriptor const *)
0x1800030e4  test    eax, eax
0x1800030e6  jz      short loc_18000315D
0x1800030e8  test    r13d, r13d
0x1800030eb  jz      short loc_18000315D
0x1800030ed  lea     r8, [rbx+1A8h]
0x1800030f4  mov     rax, [r8]
0x1800030f7  test    rax, rax
0x1800030fa  jz      short loc_18000313D
0x1800030fc  mov     [rbp+4Fh+var_A8], rax
0x180003100  mov     rcx, rax
0x180003103  mov     rdx, rax
0x180003106  neg     rcx
0x180003109  sbb     r11, r11
0x18000310c  and     r11, rdx
0x18000310f  cmp     r11, rsi
0x180003112  jz      short loc_18000312C
0x180003114  mov     rax, [rax+0C08h]
0x18000311b  mov     [rbp+4Fh+var_A8], rax
0x18000311f  mov     rcx, rax
0x180003122  mov     rdx, rax
0x180003125  test    rax, rax
  ... truncated ...
```
