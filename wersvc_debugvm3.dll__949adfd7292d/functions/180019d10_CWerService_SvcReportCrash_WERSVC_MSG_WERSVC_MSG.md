# CWerService::SvcReportCrash(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180019d10`
- end: `0x180019eeb`
- name: `?SvcReportCrash@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `475`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x180011ef8`
- `0x180014378`
- `0x180019d10`
- `0x18001a6d8`
- `0x18001ad28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ebc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::SvcReportCrash(CWerService *this, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  DWORD v6; // ebp
  DWORD v7; // r14d
  unsigned int v8; // eax
  int v9; // edi
  __int64 v10; // rdi
  __int64 i; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  HANDLE v15; // rdx
  HANDLE v16; // rcx
  int v17; // r8d
  HANDLE hObject; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v20[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v21; // [rsp+78h] [rbp-40h]

  hObject = 0;
  memset(v20, 0, sizeof(v20));
  v21 = 0;
  v6 = *((_DWORD *)a2 + 2);
  v7 = *((_DWORD *)a2 + 13);
  v8 = CWerService::CheckIfCrashIsValid(this, a2);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)a3 + 10) = 536870916;
    *((_DWORD *)a3 + 11) = -2147024891;
    *((_QWORD *)a3 + 6) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
  }
  else
  {
    v10 = 0;
    for ( i = 0; i != 5; ++i )
    {
      v12 = *((_QWORD *)a2 + i + 8);
      if ( v12 > 0 )
      {
        if ( (_DWORD)v10 )
        {
          v13 = 0;
          while ( *((_QWORD *)v20 + v13) != v12 )
          {
            v13 = (unsigned int)(v13 + 1);
            if ( (unsigned int)v13 >= (unsigned int)v10 )
              goto LABEL_12;
          }
        }
        else
        {
LABEL_12:
          *((_QWORD *)v20 + v10) = v12;
          v10 = (unsigned int)(v10 + 1);
        }
      }
    }
    v14 = CWerService::TryCaptureSnapshot((CWerService *)5, v7, v6, *((void **)a2 + 7));
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v14);
    v9 = CWerService::TryReportCrash((__int64)this, v6, v7, *((void **)a2 + 7), 0, (__int64)v20, v10, 0, 0, &hObject);
    *((_DWORD *)a3 + 11) = v9;
    v15 = hObject;
    if ( v9 < 0 )
    {
      *((_DWORD *)a3 + 10) = 536870916;
    }
    else
    {
      if ( (unsigned __int64)hObject + 1 > 1 )
      {
        v16 = hObject;
        v15 = 0;
        v17 = 536870914;
      }
      else
      {
        v16 = 0;
        v17 = 536870915;
      }
      *((_DWORD *)a3 + 10) = v17;
      *((_QWORD *)a3 + 6) = v16;
    }
    if ( (unsigned __int64)v15 + 1 > 1 )
      CloseHandle(v15);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019d10  mov     [rsp+arg_18], rbx
0x180019d15  push    rbp
0x180019d16  push    rsi
0x180019d17  push    rdi
0x180019d18  push    r14
0x180019d1a  push    r15
0x180019d1c  sub     rsp, 90h
0x180019d23  mov     rax, cs:__security_cookie
0x180019d2a  xor     rax, rsp
0x180019d2d  mov     [rsp+0B8h+var_38], rax
0x180019d35  mov     rbx, r8
0x180019d38  mov     rsi, rdx
0x180019d3b  mov     r15, rcx
0x180019d3e  mov     [rsp+0B8h+hObject], 0
0x180019d47  xorps   xmm0, xmm0
0x180019d4a  xor     eax, eax
0x180019d4c  movups  [rsp+0B8h+var_60], xmm0
0x180019d51  movups  [rsp+0B8h+var_50], xmm0
0x180019d56  mov     [rsp+0B8h+var_40], rax
0x180019d5b  mov     ebp, [rdx+8]
0x180019d5e  mov     r14d, [rdx+34h]
0x180019d62  call    ?CheckIfCrashIsValid@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::CheckIfCrashIsValid(_WERSVC_MSG *)
0x180019d67  mov     edi, eax
0x180019d69  test    eax, eax
0x180019d6b  jz      short loc_180019DBA
0x180019d6d  mov     dword ptr [rbx+28h], 20000004h
0x180019d74  mov     dword ptr [rbx+2Ch], 80070005h
0x180019d7b  mov     qword ptr [rbx+30h], 0
0x180019d83  lea     rdx, WPP_GLOBAL_Control
0x180019d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d91  cmp     rcx, rdx
0x180019d94  jz      short loc_180019DB5
0x180019d96  test    byte ptr [rcx+1Ch], 1
0x180019d9a  jz      short loc_180019DB5
0x180019d9c  mov     edx, 70h ; 'p'
0x180019da1  mov     r9d, eax
0x180019da4  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180019dab  mov     rcx, [rcx+10h]
0x180019daf  call    WPP_SF_d
0x180019db4  nop
0x180019db5  jmp     loc_180019EC2
0x180019dba  xor     edi, edi
0x180019dbc  xor     ecx, ecx
0x180019dbe  mov     r8, [rsi+rcx*8+40h]
0x180019dc3  test    r8, r8
0x180019dc6  jle     short loc_180019DE2
0x180019dc8  test    edi, edi
0x180019dca  jz      short loc_180019DDB
0x180019dcc  xor     edx, edx
0x180019dce  cmp     qword ptr [rsp+rdx*8+0B8h+var_60], r8
0x180019dd3  jz      short loc_180019DE2
0x180019dd5  inc     edx
0x180019dd7  cmp     edx, edi
0x180019dd9  jb      short loc_180019DCE
0x180019ddb  mov     qword ptr [rsp+rdi*8+0B8h+var_60], r8
0x180019de0  inc     edi
0x180019de2  inc     rcx; this
0x180019de5  cmp     rcx, 5
0x180019de9  jnz     short loc_180019DBE
0x180019deb  mov     r9, [rsi+38h]; unsigned __int64
0x180019def  mov     r8d, ebp; unsigned int
0x180019df2  mov     edx, r14d; unsigned int
0x180019df5  call    ?TryCaptureSnapshot@CWerService@@AEAAJKK_KG@Z; CWerService::TryCaptureSnapshot(ulong,ulong,unsigned __int64,ushort)
0x180019dfa  test    eax, eax
0x180019dfc  jns     short loc_180019E2F
0x180019dfe  lea     rdx, WPP_GLOBAL_Control
0x180019e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e0c  cmp     rcx, rdx
0x180019e0f  jz      short loc_180019E2F
0x180019e11  test    byte ptr [rcx+1Ch], 1
0x180019e15  jz      short loc_180019E2F
0x180019e17  mov     edx, 71h ; 'q'
0x180019e1c  mov     r9d, eax
0x180019e1f  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180019e26  mov     rcx, [rcx+10h]
0x180019e2a  call    WPP_SF_d
0x180019e2f  lea     rax, [rsp+0B8h+hObject]
0x180019e34  mov     [rsp+0B8h+var_70], rax
0x180019e39  mov     [rsp+0B8h+var_78], 0
0x180019e41  mov     [rsp+0B8h+var_80], 0
0x180019e49  mov     [rsp+0B8h+var_88], edi
0x180019e4d  lea     rax, [rsp+0B8h+var_60]
0x180019e52  mov     [rsp+0B8h+var_90], rax
0x180019e57  mov     [rsp+0B8h+var_98], 0
0x180019e60  mov     r9, [rsi+38h]
0x180019e64  mov     r8d, r14d
0x180019e67  mov     edx, ebp
0x180019e69  mov     rcx, r15
0x180019e6c  call    ?TryReportCrash@CWerService@@AEAAJKKPEAX0PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CWerService::TryReportCrash(ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *)
0x180019e71  mov     edi, eax
0x180019e73  mov     [rbx+2Ch], eax
0x180019e76  mov     rdx, [rsp+0B8h+hObject]
0x180019e7b  test    eax, eax
0x180019e7d  js      short loc_180019EA8
0x180019e7f  lea     rcx, [rdx+1]
0x180019e83  cmp     rcx, 1
0x180019e87  ja      short loc_180019E93
0x180019e89  xor     ecx, ecx
0x180019e8b  mov     r8d, 20000003h
0x180019e91  jmp     short loc_180019E9E
0x180019e93  mov     rcx, rdx
0x180019e96  xor     edx, edx
0x180019e98  mov     r8d, 20000002h
0x180019e9e  mov     [rbx+28h], r8d
0x180019ea2  mov     [rbx+30h], rcx
0x180019ea6  jmp     short loc_180019EAF
0x180019ea8  mov     dword ptr [rbx+28h], 20000004h
0x180019eaf  lea     rax, [rdx+1]
0x180019eb3  cmp     rax, 1
0x180019eb7  jbe     short loc_180019EC2
0x180019eb9  mov     rcx, rdx; hObject
0x180019ebc  call    cs:__imp_CloseHandle
0x180019ec2  mov     eax, edi
0x180019ec4  mov     rcx, [rsp+0B8h+var_38]
0x180019ecc  xor     rcx, rsp; StackCookie
0x180019ecf  call    __security_check_cookie
0x180019ed4  mov     rbx, [rsp+0B8h+arg_18]
0x180019edc  add     rsp, 90h
0x180019ee3  pop     r15
0x180019ee5  pop     r14
0x180019ee7  pop     rdi
0x180019ee8  pop     rsi
0x180019ee9  pop     rbp
0x180019eea  retn
```
