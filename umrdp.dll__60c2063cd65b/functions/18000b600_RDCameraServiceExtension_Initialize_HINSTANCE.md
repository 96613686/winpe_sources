# RDCameraServiceExtension::Initialize(HINSTANCE__ *)

- ea: `0x18000b600`
- end: `0x18000b8ef`
- name: `?Initialize@RDCameraServiceExtension@@QEAAJPEAUHINSTANCE__@@@Z`
- size: `751`
- prototype: `int(RDCameraServiceExtension *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800313a8`

## callees

- `0x180009fa8`
- `0x18000b600`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x180031890`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b88a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b652`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b652`
- `KERNEL32!CreateThreadpool` at `0x18000b7c3`
- `KERNEL32!CreateThreadpool` at `0x18000b7c3`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x18000b852`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x18000b852`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18000b858`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18000b858`

## string_xrefs

- `0x18000b80d`: `m_pThreadPool`
- `0x18000b6fc`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall RDCameraServiceExtension::Initialize(RDCameraServiceExtension *this, HINSTANCE a2)
{
  __int64 v4; // rcx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int RDCameraBus; // ebx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  struct _TP_POOL *Threadpool; // rax
  signed int v12; // eax
  char v13; // bl
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int v17; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v19; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(Buffer, 0, 0x208u);
  *((_QWORD *)this + 1) = a2;
  if ( !LoadStringW(a2, 0x834u, Buffer, 260) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      LastError = GetLastError();
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        11,
        WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    RDCameraBus = StringCchCopyW(Buffer, 0x104u, L"Remote Desktop Camera Bus");
    if ( (RDCameraBus & 0x80000000) != 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 12;
        v10 = "StringCchCopy failed";
LABEL_11:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v9,
          (unsigned int)WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
          v8,
          (__int64)v10,
          RDCameraBus);
        return RDCameraBus;
      }
      return RDCameraBus;
    }
  }
  RDCameraBus = RDCameraServiceExtension::CreateRDCameraBus(v4, Buffer, (char *)this + 16);
  if ( (RDCameraBus & 0x80000000) == 0 )
  {
    *((_DWORD *)this + 16) = 3;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
    *((_DWORD *)this + 30) = 0;
    *((_DWORD *)this + 31) = 1;
    *((_DWORD *)this + 32) = 72;
    Threadpool = CreateThreadpool(0);
    *((_QWORD *)this + 17) = Threadpool;
    if ( Threadpool )
    {
      SetThreadpoolThreadMaximum(Threadpool, 0x14u);
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *((_QWORD *)this + 18) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        *((_QWORD *)this + 9) = *((_QWORD *)this + 17);
        *((_QWORD *)this + 10) = ThreadpoolCleanupGroup;
        *((_QWORD *)this + 11) = 0;
        return RDCameraBus;
      }
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_25;
      }
      v19 = GetLastError();
      v13 = v19;
      if ( v19 > 0 )
        v13 = v19;
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 15;
      v16 = "m_pCleanupGroup";
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
LABEL_25:
        v17 = GetLastError();
        RDCameraBus = v17;
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return RDCameraBus;
      }
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = v12;
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 14;
      v16 = "m_pThreadPool";
    }
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v15,
      (unsigned int)WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
      v14,
      (__int64)v16,
      v13);
    goto LABEL_25;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 13;
    v10 = "spUMBusDriver->FindEnumByIdentity failed";
    goto LABEL_11;
  }
  return RDCameraBus;
}

```

## disassembly

```asm
0x18000b600  mov     [rsp+arg_10], rbx
0x18000b605  push    rdi
0x18000b606  push    r14
0x18000b608  push    r15
0x18000b60a  sub     rsp, 250h
0x18000b611  mov     rax, cs:__security_cookie
0x18000b618  xor     rax, rsp
0x18000b61b  mov     [rsp+268h+var_28], rax
0x18000b623  mov     rbx, rdx
0x18000b626  mov     rdi, rcx
0x18000b629  xor     edx, edx; Val
0x18000b62b  lea     rcx, [rsp+268h+Buffer]; void *
0x18000b630  mov     r8d, 208h; Size
0x18000b636  call    memset_0
0x18000b63b  mov     r9d, 104h; cchBufferMax
0x18000b641  mov     [rdi+8], rbx
0x18000b645  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x18000b64a  mov     edx, 834h; uID
0x18000b64f  mov     rcx, rbx; hInstance
0x18000b652  call    cs:__imp_LoadStringW
0x18000b658  lea     r14, WPP_GLOBAL_Control
0x18000b65f  lea     r15, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x18000b666  test    eax, eax
0x18000b668  jnz     loc_18000B727
0x18000b66e  mov     rax, cs:WPP_GLOBAL_Control
0x18000b675  cmp     rax, r14
0x18000b678  jz      short loc_18000B6B2
0x18000b67a  test    byte ptr [rax+1Ch], 1
0x18000b67e  jz      short loc_18000B6B2
0x18000b680  cmp     byte ptr [rax+19h], 2
0x18000b684  jb      short loc_18000B6B2
0x18000b686  call    cs:__imp_GetLastError
0x18000b68c  mov     ebx, eax
0x18000b68e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b693  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b69a  mov     edx, 0Bh
0x18000b69f  mov     r9d, eax
0x18000b6a2  mov     dword ptr [rsp+268h+var_248], ebx
0x18000b6a6  mov     r8, r15
0x18000b6a9  mov     rcx, [rcx+10h]
0x18000b6ad  call    WPP_SF_Dd
0x18000b6b2  lea     r8, aRemoteDesktopC; "Remote Desktop Camera Bus"
0x18000b6b9  mov     edx, 104h; unsigned __int64
0x18000b6be  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x18000b6c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b6c8  mov     ebx, eax
0x18000b6ca  test    eax, eax
0x18000b6cc  jns     short loc_18000B727
0x18000b6ce  mov     rax, cs:WPP_GLOBAL_Control
0x18000b6d5  cmp     rax, r14
0x18000b6d8  jz      loc_18000B8C8
0x18000b6de  test    byte ptr [rax+1Ch], 8
0x18000b6e2  jz      loc_18000B8C8
0x18000b6e8  cmp     byte ptr [rax+19h], 2
0x18000b6ec  jb      loc_18000B8C8
0x18000b6f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b6f7  mov     edx, 0Ch
0x18000b6fc  lea     rcx, aStringcchcopyF; "StringCchCopy failed"
0x18000b703  mov     [rsp+268h+var_240], ebx
0x18000b707  mov     r9d, eax
0x18000b70a  mov     [rsp+268h+var_248], rcx
0x18000b70f  mov     r8, r15
0x18000b712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b719  mov     rcx, [rcx+10h]
0x18000b71d  call    WPP_SF_DsD
0x18000b722  jmp     loc_18000B8C8
0x18000b727  lea     r8, [rdi+10h]
0x18000b72b  lea     rdx, [rsp+268h+Buffer]
0x18000b730  call    ?CreateRDCameraBus@RDCameraServiceExtension@@AEAAJPEBGAEAV?$shared_ptr@VITsBus@@@utl@@@Z; RDCameraServiceExtension::CreateRDCameraBus(ushort const *,utl::shared_ptr<ITsBus> &)
0x18000b735  mov     ebx, eax
0x18000b737  test    eax, eax
0x18000b739  jns     short loc_18000B772
0x18000b73b  mov     rax, cs:WPP_GLOBAL_Control
0x18000b742  cmp     rax, r14
0x18000b745  jz      loc_18000B8C8
0x18000b74b  test    byte ptr [rax+1Ch], 8
0x18000b74f  jz      loc_18000B8C8
0x18000b755  cmp     byte ptr [rax+19h], 2
0x18000b759  jb      loc_18000B8C8
0x18000b75f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b764  mov     edx, 0Dh
0x18000b769  lea     rcx, aSpumbusdriverF; "spUMBusDriver->FindEnumByIdentity faile"...
0x18000b770  jmp     short loc_18000B703
0x18000b772  xor     ecx, ecx; reserved
0x18000b774  mov     dword ptr [rdi+40h], 3
0x18000b77b  mov     qword ptr [rdi+48h], 0
0x18000b783  mov     qword ptr [rdi+50h], 0
0x18000b78b  mov     qword ptr [rdi+58h], 0
0x18000b793  mov     qword ptr [rdi+60h], 0
0x18000b79b  mov     qword ptr [rdi+68h], 0
0x18000b7a3  mov     qword ptr [rdi+70h], 0
0x18000b7ab  mov     dword ptr [rdi+78h], 0
0x18000b7b2  mov     dword ptr [rdi+7Ch], 1
0x18000b7b9  mov     dword ptr [rdi+80h], 48h ; 'H'
0x18000b7c3  call    cs:__imp_CreateThreadpool
0x18000b7c9  mov     [rdi+88h], rax
0x18000b7d0  test    rax, rax
0x18000b7d3  jnz     short loc_18000B84A
0x18000b7d5  mov     rax, cs:WPP_GLOBAL_Control
0x18000b7dc  mov     edi, 80070000h
0x18000b7e1  cmp     rax, r14
0x18000b7e4  jz      short loc_18000B833
0x18000b7e6  test    byte ptr [rax+1Ch], 8
0x18000b7ea  jz      short loc_18000B833
0x18000b7ec  cmp     byte ptr [rax+19h], 2
0x18000b7f0  jb      short loc_18000B833
0x18000b7f2  call    cs:__imp_GetLastError
0x18000b7f8  mov     ebx, eax
0x18000b7fa  test    eax, eax
0x18000b7fc  jle     short loc_18000B803
0x18000b7fe  movzx   ebx, ax
0x18000b801  or      ebx, edi
0x18000b803  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b808  mov     edx, 0Eh
0x18000b80d  lea     rcx, aMPthreadpool; "m_pThreadPool"
0x18000b814  mov     [rsp+268h+var_240], ebx
0x18000b818  mov     r9d, eax
0x18000b81b  mov     [rsp+268h+var_248], rcx
0x18000b820  mov     r8, r15
0x18000b823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b82a  mov     rcx, [rcx+10h]
0x18000b82e  call    WPP_SF_DsD
0x18000b833  call    cs:__imp_GetLastError
0x18000b839  mov     ebx, eax
0x18000b83b  test    eax, eax
0x18000b83d  jle     loc_18000B8C8
0x18000b843  movzx   ebx, ax
0x18000b846  or      ebx, edi
0x18000b848  jmp     short loc_18000B8C8
0x18000b84a  mov     edx, 14h; cthrdMost
0x18000b84f  mov     rcx, rax; ptpp
0x18000b852  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000b858  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000b85e  mov     [rdi+90h], rax
0x18000b865  mov     rcx, rax
0x18000b868  test    rax, rax
0x18000b86b  jnz     short loc_18000B8B1
0x18000b86d  mov     rax, cs:WPP_GLOBAL_Control
0x18000b874  mov     edi, 80070000h
0x18000b879  cmp     rax, r14
0x18000b87c  jz      short loc_18000B833
0x18000b87e  test    byte ptr [rax+1Ch], 8
0x18000b882  jz      short loc_18000B833
0x18000b884  cmp     byte ptr [rax+19h], 2
0x18000b888  jb      short loc_18000B833
0x18000b88a  call    cs:__imp_GetLastError
0x18000b890  mov     ebx, eax
0x18000b892  test    eax, eax
0x18000b894  jle     short loc_18000B89B
0x18000b896  movzx   ebx, ax
0x18000b899  or      ebx, edi
0x18000b89b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b8a0  mov     edx, 0Fh
0x18000b8a5  lea     rcx, aMPcleanupgroup; "m_pCleanupGroup"
0x18000b8ac  jmp     loc_18000B814
0x18000b8b1  mov     rax, [rdi+88h]
0x18000b8b8  mov     [rdi+48h], rax
0x18000b8bc  mov     [rdi+50h], rcx
0x18000b8c0  mov     qword ptr [rdi+58h], 0
0x18000b8c8  mov     eax, ebx
0x18000b8ca  mov     rcx, [rsp+268h+var_28]
0x18000b8d2  xor     rcx, rsp; StackCookie
0x18000b8d5  call    __security_check_cookie
0x18000b8da  mov     rbx, [rsp+268h+arg_10]
0x18000b8e2  add     rsp, 250h
0x18000b8e9  pop     r15
0x18000b8eb  pop     r14
0x18000b8ed  pop     rdi
0x18000b8ee  retn
```
