# CopyStream(IStream *,IStream * *)

- ea: `0x180043e8c`
- end: `0x180044016`
- name: `?CopyStream@@YAJPEAUIStream@@PEAPEAU1@@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct IStream *pstm, struct IStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043c68`

## callees

- `0x180006800`
- `0x180013f14`
- `0x18003ff34`
- `0x180043e8c`
- `0x18004401c`
- `0x180044054`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180043f4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180043f4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180043f74`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180043f74`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043fdf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043fef`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043fdf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043fef`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180043ee9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180043ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043fb2`

## string_xrefs

- `0x180043f2f`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180043f8f`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180043fce`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyStream(struct IStream *pstm, struct IStream **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  wil::details::in1diag3 *v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  HRESULT v14; // eax
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  IStream *pstma; // [rsp+48h] [rbp+28h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+30h] BYREF
  void *pv; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  pstma = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&pstma);
  v6 = SHCreateMemoryStream(v5, v4, &pstma);
  v7 = v6;
  v8 = retaddr;
  if ( v6 < 0 )
  {
    v9 = (unsigned int)v6;
    v10 = 159;
    goto LABEL_17;
  }
  pui.QuadPart = 0;
  v11 = IStream_Size(pstm, &pui);
  v7 = v11;
  v12 = retaddr;
  if ( v11 >= 0 )
  {
    pv = 0;
    v11 = CTCoAllocPolicy::Alloc(retaddr, 1u, pui.LowPart, &pv);
    v7 = v11;
    v12 = retaddr;
    if ( v11 < 0 )
    {
      v13 = 169;
      goto LABEL_7;
    }
    v14 = IStream_Read(pstm, pv, pui.LowPart);
    v7 = v14;
    v15 = retaddr;
    if ( v14 >= 0 )
    {
      v14 = IStream_Write(pstma, pv, pui.LowPart);
      v7 = v14;
      v15 = retaddr;
      if ( v14 >= 0 )
      {
        v7 = Microsoft::WRL::ComPtr<IStream>::CopyTo(&pstma, v17, a2);
        goto LABEL_14;
      }
      v16 = 175;
    }
    else
    {
      v16 = 172;
    }
    wil::details::in1diag3::_Log_Hr(
      v15,
      (void *)v16,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v14,
      savedregs);
LABEL_14:
    CoTaskMemFree(pv);
    goto LABEL_15;
  }
  v13 = 163;
LABEL_7:
  wil::details::in1diag3::_Log_Hr(
    v12,
    (void *)v13,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)(unsigned int)v11,
    savedregs);
LABEL_15:
  v8 = retaddr;
  if ( v7 >= 0 )
  {
    IStream_Reset(pstm);
    IStream_Reset(pstma);
    goto LABEL_19;
  }
  v9 = (unsigned int)v7;
  v10 = 184;
LABEL_17:
  wil::details::in1diag3::_Log_Hr(
    v8,
    (void *)v10,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)v9,
    savedregs);
LABEL_19:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&pstma);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180043e8c  mov     [rsp-18h+arg_0], rbx
0x180043e91  push    rbp
0x180043e92  push    rdi
0x180043e93  push    r14; int
0x180043e95  mov     rbp, rsp
0x180043e98  sub     rsp, 20h
0x180043e9c  mov     r14, rdx
0x180043e9f  mov     rdi, rcx
0x180043ea2  mov     qword ptr [rdx], 0
0x180043ea9  mov     [rbp+pstm], 0
0x180043eb1  lea     rcx, [rbp+pstm]
0x180043eb5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180043eba  lea     r8, [rbp+pstm]
0x180043ebe  call    SHCreateMemoryStream
0x180043ec3  mov     ebx, eax
0x180043ec5  mov     rcx, [rbp+18h]
0x180043ec9  test    eax, eax
0x180043ecb  jns     short loc_180043EDA
0x180043ecd  mov     r9d, eax
0x180043ed0  mov     edx, 9Fh
0x180043ed5  jmp     loc_180043FCE
0x180043eda  mov     qword ptr [rbp+pui], 0
0x180043ee2  lea     rdx, [rbp+pui]; pui
0x180043ee6  mov     rcx, rdi; pstm
0x180043ee9  call    cs:__imp_IStream_Size
0x180043ef0  nop     dword ptr [rax+rax+00h]
0x180043ef5  mov     ebx, eax
0x180043ef7  mov     rcx, [rbp+18h]; void *
0x180043efb  test    eax, eax
0x180043efd  jns     short loc_180043F06
0x180043eff  mov     edx, 0A3h
0x180043f04  jmp     short loc_180043F2F
0x180043f06  mov     [rbp+pv], 0
0x180043f0e  mov     r8d, dword ptr [rbp+pui]; unsigned __int64
0x180043f12  lea     r9, [rbp+pv]; void **
0x180043f16  mov     edx, 1; unsigned int
0x180043f1b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180043f20  mov     ebx, eax
0x180043f22  mov     rcx, [rbp+18h]; this
0x180043f26  test    eax, eax
0x180043f28  jns     short loc_180043F40
0x180043f2a  mov     edx, 0A9h; void *
0x180043f2f  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180043f36  mov     r9d, eax; char *
0x180043f39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043f3e  jmp     short loc_180043FBE
0x180043f40  mov     r8d, dword ptr [rbp+pui]; cb
0x180043f44  mov     rdx, [rbp+pv]; pv
0x180043f48  mov     rcx, rdi; pstm
0x180043f4b  call    cs:__imp_IStream_Read
0x180043f52  nop     dword ptr [rax+rax+00h]
0x180043f57  mov     ebx, eax
0x180043f59  mov     rcx, [rbp+18h]
0x180043f5d  test    eax, eax
0x180043f5f  jns     short loc_180043F68
0x180043f61  mov     edx, 0ACh
0x180043f66  jmp     short loc_180043F8F
0x180043f68  mov     r8d, dword ptr [rbp+pui]; cb
0x180043f6c  mov     rdx, [rbp+pv]; pv
0x180043f70  mov     rcx, [rbp+pstm]; pstm
0x180043f74  call    cs:__imp_IStream_Write
0x180043f7b  nop     dword ptr [rax+rax+00h]
0x180043f80  mov     ebx, eax
0x180043f82  mov     rcx, [rbp+18h]; this
0x180043f86  test    eax, eax
0x180043f88  jns     short loc_180043FA0
0x180043f8a  mov     edx, 0AFh; void *
0x180043f8f  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180043f96  mov     r9d, eax; char *
0x180043f99  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043f9e  jmp     short loc_180043FAE
0x180043fa0  mov     r8, r14
0x180043fa3  lea     rcx, [rbp+pstm]
0x180043fa7  call    ?CopyTo@?$ComPtr@UIStream@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IStream>::CopyTo(_GUID const &,void * *)
0x180043fac  mov     ebx, eax
0x180043fae  mov     rcx, [rbp+pv]; pv
0x180043fb2  call    cs:__imp_CoTaskMemFree
0x180043fb9  nop     dword ptr [rax+rax+00h]
0x180043fbe  mov     rcx, [rbp+18h]; this
0x180043fc2  test    ebx, ebx
0x180043fc4  jns     short loc_180043FDC
0x180043fc6  mov     r9d, ebx; char *
0x180043fc9  mov     edx, 0B8h; void *
0x180043fce  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180043fd5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043fda  jmp     short loc_180043FFC
0x180043fdc  mov     rcx, rdi; pstm
0x180043fdf  call    cs:__imp_IStream_Reset
0x180043fe6  nop     dword ptr [rax+rax+00h]
0x180043feb  mov     rcx, [rbp+pstm]; pstm
0x180043fef  call    cs:__imp_IStream_Reset
0x180043ff6  nop     dword ptr [rax+rax+00h]
0x180043ffb  nop
0x180043ffc  lea     rcx, [rbp+pstm]
0x180044000  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180044005  mov     eax, ebx
0x180044007  mov     rbx, [rsp+20h+arg_0]
0x18004400c  add     rsp, 20h
0x180044010  pop     r14
0x180044012  pop     rdi
0x180044013  pop     rbp
0x180044014  retn
```
