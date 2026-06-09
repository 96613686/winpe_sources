# SBE2PauseBuffer::CSBEXP::CreateHeader(void)

- ea: `0x1800aeb28`
- end: `0x1800aedec`
- name: `?CreateHeader@CSBEXP@SBE2PauseBuffer@@AEAAJXZ`
- size: `708`
- prototype: `__int64 __fastcall(SBE2PauseBuffer::CSBEXP *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800ae184`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x18002573c`
- `0x180060ab0`
- `0x180060af8`
- `0x180061628`
- `0x180061ef0`
- `0x1800627f0`
- `0x1800ae5d4`
- `0x1800ae918`
- `0x1800aeb28`
- `0x1800aefc8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800aec14`
- `KERNEL32!GetLastError` at `0x1800aec64`
- `KERNEL32!GetLastError` at `0x1800aec14`
- `KERNEL32!GetLastError` at `0x1800aec64`
- `KERNEL32!SetFilePointerEx` at `0x1800aec0a`
- `KERNEL32!SetFilePointerEx` at `0x1800aec0a`
- `KERNEL32!WriteFile` at `0x1800aec5a`
- `KERNEL32!WriteFile` at `0x1800aec5a`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CSBEXP::CreateHeader(SBE2PauseBuffer::CSBEXP *this)
{
  SBECoreUtil *v2; // rcx
  unsigned __int16 *v3; // r9
  unsigned int v4; // r14d
  SBECoreUtil::CMutexLock **v5; // rdi
  int LowPart; // ebx
  int Instance; // eax
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  HANDLE *v10; // rcx
  signed int LastError; // eax
  unsigned int v12; // edx
  signed int v13; // eax
  unsigned __int64 v14; // rdx
  SBE2PauseBuffer::CUnalignedMemMap *v15; // rax
  SBE2PauseBuffer::CUnalignedMemMap *v16; // rax
  SBE2PauseBuffer::CUnalignedMemMap *v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // edx
  SBE2PauseBuffer::CUnalignedMemMap *v20; // rcx
  LARGE_INTEGER liDistanceToMove; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v25; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v26; // [rsp+A0h] [rbp-60h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(&Buffer, 0, 0x40u);
  v4 = 0;
  v5 = (SBECoreUtil::CMutexLock **)((char *)this + 320);
  while ( 1 )
  {
    LowPart = SBECoreUtil::CreateGlobalUniqueString(v2, (unsigned int)&v25, &v26, v3);
    if ( LowPart < 0 )
      goto LABEL_27;
    v5 = (SBECoreUtil::CMutexLock **)((char *)this + 320);
    SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 320);
    Instance = SBECoreUtil::CMutexLock::CreateInstance(
                 (LPCWSTR)&v26,
                 *((struct SBECoreUtil::CW32SID **)this + 39),
                 1u,
                 1,
                 (struct CMutexLock **)this + 40);
    LowPart = Instance;
    if ( Instance >= 0 )
      break;
    if ( v4 >= 0x10 )
    {
      v8 = Instance;
      v9 = 498;
      goto LABEL_17;
    }
    ++v4;
  }
  v10 = (HANDLE *)*((_QWORD *)this + 37);
  liDistanceToMove.QuadPart = 0;
  Buffer = xmmword_1800CBE40;
  if ( !SetFilePointerEx(*v10, 0, 0, 0) )
  {
    LastError = GetLastError();
    LowPart = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        LowPart = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
      if ( LowPart >= 0 )
        return (unsigned int)LowPart;
      goto LABEL_28;
    }
  }
  if ( WriteFile(**((HANDLE **)this + 37), &Buffer, 0x40u, &NumberOfBytesWritten, 0) )
  {
    liDistanceToMove.LowPart = SBE2PauseBuffer::CSBEXP::FormHeaderMMName(this, v12, (unsigned __int16 *)&v26);
    LowPart = liDistanceToMove.LowPart;
    if ( (liDistanceToMove.LowPart & 0x80000000) != 0 )
      goto LABEL_27;
    v15 = (SBE2PauseBuffer::CUnalignedMemMap *)SBECoreUtil::New((SBECoreUtil *)0x18, v14);
    if ( v15 )
    {
      v16 = (SBE2PauseBuffer::CUnalignedMemMap *)SBE2PauseBuffer::CUnalignedMemMap::CUnalignedMemMap(
                                                   v15,
                                                   (const unsigned __int16 *)&v26,
                                                   **((void ***)this + 37),
                                                   *((_DWORD *)this + 82),
                                                   1u,
                                                   *((struct SBECoreUtil::CW32SID **)this + 39),
                                                   0x40u,
                                                   0,
                                                   (int *)&liDistanceToMove);
      LowPart = liDistanceToMove.LowPart;
      v17 = v16;
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)this + 36) = v17;
    if ( !v17 )
    {
      LowPart = -2147024882;
LABEL_28:
      if ( *v5 )
        SBECoreUtil::CMutexLock::Unlock(*v5);
      SAL2::Release<SAL2::CSALResidentNVP *>(v5);
      v20 = (SBE2PauseBuffer::CUnalignedMemMap *)*((_QWORD *)this + 36);
      if ( v20 )
        SBE2PauseBuffer::CUnalignedMemMap::`scalar deleting destructor'(v20, v19);
      *((_QWORD *)this + 36) = 0;
      SBEBasicTracers::EtwTraceError(
        (SBE2PauseBuffer::CSBEXP *)((char *)this + 104),
        "multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
        0x268u,
        LowPart);
      *((_QWORD *)this + 38) = 0;
      return (unsigned int)LowPart;
    }
    if ( LowPart >= 0 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)v17 + 528LL) + *((_QWORD *)v17 + 1);
      *((_QWORD *)this + 38) = v18;
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 56));
      goto LABEL_27;
    }
    SBE2PauseBuffer::CUnalignedMemMap::`scalar deleting destructor'(v17, (unsigned int)v17);
    v9 = 585;
    *((_QWORD *)this + 36) = 0;
LABEL_16:
    v8 = LowPart;
LABEL_17:
    SBEBasicTracers::EtwTraceError(
      (SBE2PauseBuffer::CSBEXP *)((char *)this + 104),
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\sbexp.cpp",
      v9,
      v8);
    goto LABEL_27;
  }
  v13 = GetLastError();
  LowPart = v13;
  if ( v13 > 0 )
    LowPart = (unsigned __int16)v13 | 0x80070000;
  if ( LowPart < 0 )
  {
    v9 = 545;
    goto LABEL_16;
  }
  return (unsigned int)LowPart;
}

```

## disassembly

```asm
0x1800aeb28  mov     [rsp-8+arg_8], rbx
0x1800aeb2d  mov     [rsp-8+arg_10], rsi
0x1800aeb32  push    rbp
0x1800aeb33  push    rdi
0x1800aeb34  push    r14
0x1800aeb36  lea     rbp, [rsp-1C0h]
0x1800aeb3e  sub     rsp, 2C0h
0x1800aeb45  mov     rax, cs:__security_cookie
0x1800aeb4c  xor     rax, rsp
0x1800aeb4f  mov     [rbp+1D0h+var_20], rax
0x1800aeb56  xor     edx, edx; Val
0x1800aeb58  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x1800aeb60  mov     rsi, rcx
0x1800aeb63  lea     rcx, [rsp+2D0h+Buffer]; void *
0x1800aeb68  lea     r8d, [rdx+40h]; Size
0x1800aeb6c  call    memset_0
0x1800aeb71  xor     r14d, r14d
0x1800aeb74  lea     rdi, [rsi+140h]
0x1800aeb7b  lea     r8, [rbp+1D0h+var_230]; struct _GUID *
0x1800aeb7f  lea     rdx, [rsp+2D0h+var_260]; unsigned int
0x1800aeb84  call    ?CreateGlobalUniqueString@SBECoreUtil@@YAJKPEAU_GUID@@PEAG@Z; SBECoreUtil::CreateGlobalUniqueString(ulong,_GUID *,ushort *)
0x1800aeb89  mov     ebx, eax
0x1800aeb8b  test    eax, eax
0x1800aeb8d  js      loc_1800AED6A
0x1800aeb93  lea     rdi, [rsi+140h]
0x1800aeb9a  mov     rcx, rdi
0x1800aeb9d  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aeba2  mov     rdx, [rsi+138h]; struct SBECoreUtil::CW32SID *
0x1800aeba9  lea     rcx, [rbp+1D0h+var_230]; lpName
0x1800aebad  mov     r9d, 1; int
0x1800aebb3  mov     [rsp+2D0h+lpOverlapped], rdi; struct CMutexLock **
0x1800aebb8  mov     r8d, r9d; unsigned int
0x1800aebbb  call    ?CreateInstance@CMutexLock@SBECoreUtil@@SAJPEAGPEAVCW32SID@2@KHPEAPEAV12@@Z; SBECoreUtil::CMutexLock::CreateInstance(ushort *,SBECoreUtil::CW32SID *,ulong,int,SBECoreUtil::CMutexLock * *)
0x1800aebc0  mov     ebx, eax
0x1800aebc2  test    eax, eax
0x1800aebc4  jns     short loc_1800AEBDF
0x1800aebc6  cmp     r14d, 10h
0x1800aebca  jnb     short loc_1800AEBD1
0x1800aebcc  inc     r14d
0x1800aebcf  jmp     short loc_1800AEB7B
0x1800aebd1  mov     r9d, eax
0x1800aebd4  mov     r8d, 1F2h
0x1800aebda  jmp     loc_1800AEC8A
0x1800aebdf  movups  xmm0, cs:xmmword_1800CBE40
0x1800aebe6  mov     rcx, [rsi+128h]
0x1800aebed  xor     r9d, r9d; dwMoveMethod
0x1800aebf0  mov     qword ptr [rsp+2D0h+liDistanceToMove], 0
0x1800aebf9  xor     r8d, r8d; lpNewFilePointer
0x1800aebfc  mov     rdx, qword ptr [rsp+2D0h+liDistanceToMove]; liDistanceToMove
0x1800aec01  movdqu  [rsp+2D0h+Buffer], xmm0
0x1800aec07  mov     rcx, [rcx]; hFile
0x1800aec0a  call    cs:__imp_SetFilePointerEx
0x1800aec10  test    eax, eax
0x1800aec12  jnz     short loc_1800AEC34
0x1800aec14  call    cs:__imp_GetLastError
0x1800aec1a  mov     ebx, eax
0x1800aec1c  test    eax, eax
0x1800aec1e  jz      short loc_1800AEC34
0x1800aec20  jle     loc_1800AED6A
0x1800aec26  movzx   ebx, ax
0x1800aec29  or      ebx, 80070000h
0x1800aec2f  jmp     loc_1800AED6A
0x1800aec34  mov     rcx, [rsi+128h]
0x1800aec3b  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800aec40  mov     r14d, 40h ; '@'
0x1800aec46  mov     [rsp+2D0h+lpOverlapped], 0; lpOverlapped
0x1800aec4f  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800aec52  lea     rdx, [rsp+2D0h+Buffer]; lpBuffer
0x1800aec57  mov     rcx, [rcx]; hFile
0x1800aec5a  call    cs:__imp_WriteFile
0x1800aec60  test    eax, eax
0x1800aec62  jnz     short loc_1800AEC9F
0x1800aec64  call    cs:__imp_GetLastError
0x1800aec6a  mov     ebx, eax
0x1800aec6c  test    eax, eax
0x1800aec6e  jle     short loc_1800AEC79
0x1800aec70  movzx   ebx, ax
0x1800aec73  or      ebx, 80070000h
0x1800aec79  test    ebx, ebx
0x1800aec7b  jns     loc_1800AEDC3
0x1800aec81  mov     r8d, 221h; unsigned int
0x1800aec87  mov     r9d, ebx; unsigned int
0x1800aec8a  lea     rcx, [rsi+68h]; struct CEhEventTracer *
0x1800aec8e  lea     rdx, aMultimediaDsho_17; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aec95  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aec9a  jmp     loc_1800AED6A
0x1800aec9f  lea     r8, [rbp+1D0h+var_230]; unsigned __int16 *
0x1800aeca3  mov     rcx, rsi; this
0x1800aeca6  call    ?FormHeaderMMName@CSBEXP@SBE2PauseBuffer@@AEAAJKPEAG@Z; SBE2PauseBuffer::CSBEXP::FormHeaderMMName(ulong,ushort *)
0x1800aecab  mov     dword ptr [rsp+2D0h+liDistanceToMove], eax
0x1800aecaf  mov     ebx, eax
0x1800aecb1  test    eax, eax
0x1800aecb3  js      loc_1800AED6A
0x1800aecb9  mov     ecx, 18h; this
0x1800aecbe  call    ?New@SBECoreUtil@@YAPEAX_K@Z; SBECoreUtil::New(unsigned __int64)
0x1800aecc3  test    rax, rax
0x1800aecc6  jz      short loc_1800AED1A
0x1800aecc8  mov     r8, [rsi+128h]
0x1800aeccf  lea     rcx, [rsp+2D0h+liDistanceToMove]
0x1800aecd4  mov     r9d, [rsi+148h]; unsigned int
0x1800aecdb  lea     rdx, [rbp+1D0h+var_230]; unsigned __int16 *
0x1800aecdf  mov     [rsp+2D0h+var_290], rcx; int *
0x1800aece4  mov     rcx, [rsi+138h]
0x1800aeceb  mov     r8, [r8]; void *
0x1800aecee  mov     [rsp+2D0h+var_298], 0; unsigned __int64
0x1800aecf7  mov     [rsp+2D0h+var_2A0], r14; unsigned __int64
0x1800aecfc  mov     [rsp+2D0h+var_2A8], rcx; struct SBECoreUtil::CW32SID *
0x1800aed01  mov     rcx, rax; this
0x1800aed04  mov     dword ptr [rsp+2D0h+lpOverlapped], 1; unsigned int
0x1800aed0c  call    ??0CUnalignedMemMap@SBE2PauseBuffer@@QEAA@PEBGPEAXKKPEAVCW32SID@SBECoreUtil@@_K3PEAJ@Z; SBE2PauseBuffer::CUnalignedMemMap::CUnalignedMemMap(ushort const *,void *,ulong,ulong,SBECoreUtil::CW32SID *,unsigned __int64,unsigned __int64,long *)
0x1800aed11  mov     ebx, dword ptr [rsp+2D0h+liDistanceToMove]
0x1800aed15  mov     rdx, rax
0x1800aed18  jmp     short loc_1800AED1C
0x1800aed1a  xor     edx, edx; unsigned int
0x1800aed1c  mov     [rsi+120h], rdx
0x1800aed23  test    rdx, rdx
0x1800aed26  jnz     short loc_1800AED2F
0x1800aed28  mov     ebx, 8007000Eh
0x1800aed2d  jmp     short loc_1800AED6E
0x1800aed2f  test    ebx, ebx
0x1800aed31  jns     short loc_1800AED51
0x1800aed33  mov     rcx, rdx; this
0x1800aed36  call    ??_GCUnalignedMemMap@SBE2PauseBuffer@@QEAAPEAXI@Z; SBE2PauseBuffer::CUnalignedMemMap::`scalar deleting destructor'(uint)
0x1800aed3b  mov     r8d, 249h
0x1800aed41  mov     qword ptr [rsi+120h], 0
0x1800aed4c  jmp     loc_1800AEC87
0x1800aed51  mov     rax, [rdx]
0x1800aed54  mov     rdx, [rdx+8]
0x1800aed58  add     rdx, [rax+210h]
0x1800aed5f  mov     [rsi+130h], rdx
0x1800aed66  lock inc dword ptr [rdx+38h]
0x1800aed6a  test    ebx, ebx
0x1800aed6c  jns     short loc_1800AEDC3
0x1800aed6e  mov     rcx, [rdi]; this
0x1800aed71  test    rcx, rcx
0x1800aed74  jz      short loc_1800AED7B
0x1800aed76  call    ?Unlock@CMutexLock@SBECoreUtil@@QEAAXXZ; SBECoreUtil::CMutexLock::Unlock(void)
0x1800aed7b  mov     rcx, rdi
0x1800aed7e  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aed83  mov     rcx, [rsi+120h]; this
0x1800aed8a  test    rcx, rcx
0x1800aed8d  jz      short loc_1800AED94
0x1800aed8f  call    ??_GCUnalignedMemMap@SBE2PauseBuffer@@QEAAPEAXI@Z; SBE2PauseBuffer::CUnalignedMemMap::`scalar deleting destructor'(uint)
0x1800aed94  lea     rcx, [rsi+68h]; struct CEhEventTracer *
0x1800aed98  mov     qword ptr [rsi+120h], 0
0x1800aeda3  mov     r9d, ebx; unsigned int
0x1800aeda6  lea     rdx, aMultimediaDsho_17; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aedad  mov     r8d, 268h; unsigned int
0x1800aedb3  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aedb8  mov     qword ptr [rsi+130h], 0
0x1800aedc3  mov     eax, ebx
0x1800aedc5  mov     rcx, [rbp+1D0h+var_20]
0x1800aedcc  xor     rcx, rsp; StackCookie
0x1800aedcf  call    __security_check_cookie
0x1800aedd4  lea     r11, [rsp+2D0h+var_10]
0x1800aeddc  mov     rbx, [r11+28h]
0x1800aede0  mov     rsi, [r11+30h]
0x1800aede4  mov     rsp, r11
0x1800aede7  pop     r14
0x1800aede9  pop     rdi
0x1800aedea  pop     rbp
0x1800aedeb  retn
```
