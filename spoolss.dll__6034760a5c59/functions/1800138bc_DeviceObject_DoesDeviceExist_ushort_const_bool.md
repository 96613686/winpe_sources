# DeviceObject::DoesDeviceExist(ushort const *,bool *)

- ea: `0x1800138bc`
- end: `0x180013a5e`
- name: `?DoesDeviceExist@DeviceObject@@SAJPEBGPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048b4`

## callees

- `0x180011c98`
- `0x180012344`
- `0x180013200`
- `0x1800138bc`
- `0x180013c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800139ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800139ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001392f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001392f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001394b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001394b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a0b`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180013a30`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180013a30`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x1800139d0`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x1800139d0`

## pseudocode

```c
__int64 __fastcall DeviceObject::DoesDeviceExist(const unsigned __int16 *a1, bool *a2)
{
  unsigned __int16 near **v2; // rbx
  signed int ObjectQueryFromId; // edi
  int v5; // eax
  __int64 v6; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  DWORD v9; // eax
  signed int v10; // eax
  NCoreLibrary::TString *v11; // rcx
  __int64 v13; // [rsp+98h] [rbp+28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h]

  v2 = &NCoreLibrary::TString::gszNullState;
  if ( a2 )
  {
    *a2 = 0;
    v13 = (__int64)&NCoreLibrary::TString::gszNullState;
    v5 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v13, L"SWD\\PRINTENUM\\%ws", a1);
    v2 = (unsigned __int16 near **)v13;
    ObjectQueryFromId = v5;
  }
  else
  {
    ObjectQueryFromId = -2147024809;
  }
  v13 = -1;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  v6 = -1;
  v13 = -1;
  if ( ObjectQueryFromId >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    NCoreLibrary::TAutoHandleNT::operator=(&v13, EventW);
    v6 = v13;
    if ( v13 == -1 )
    {
      LastError = GetLastError();
      ObjectQueryFromId = LastError;
      if ( LastError > 0 )
        ObjectQueryFromId = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v14 = 0;
  if ( ObjectQueryFromId >= 0 )
  {
    ObjectQueryFromId = DevCreateObjectQueryFromId(3, v2, 0);
    if ( ObjectQueryFromId >= 0 )
    {
      if ( v6 == -1 )
        v6 = 0;
      v9 = WaitForSingleObject((HANDLE)v6, 0xFFFFFFFF);
      if ( v9 )
      {
        if ( v9 == -1 )
        {
          v10 = GetLastError();
          ObjectQueryFromId = v10;
          if ( v10 > 0 )
            ObjectQueryFromId = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          ObjectQueryFromId = -2147418113;
        }
      }
      else
      {
        ObjectQueryFromId = 0;
        *a2 = 0;
      }
    }
    if ( v14 )
      DevCloseObjectQuery();
  }
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v13);
  NCoreLibrary::TString::vFree(v11, v2);
  return (unsigned int)ObjectQueryFromId;
}

```

## disassembly

```asm
0x1800138bc  mov     [rsp-18h+arg_0], rbx
0x1800138c1  mov     [rsp-18h+arg_18], rsi
0x1800138c6  push    rbp
0x1800138c7  push    rdi
0x1800138c8  push    r14
0x1800138ca  mov     rbp, rsp
0x1800138cd  sub     rsp, 70h
0x1800138d1  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800138d8  mov     r14, rdx
0x1800138db  test    rdx, rdx
0x1800138de  jnz     short loc_1800138E7
0x1800138e0  mov     edi, 80070057h
0x1800138e5  jmp     short loc_180013907
0x1800138e7  mov     byte ptr [rdx], 0
0x1800138ea  mov     r8, rcx
0x1800138ed  lea     rdx, aSwdPrintenumWs; "SWD\\PRINTENUM\\%ws"
0x1800138f4  mov     [rbp+arg_8], rbx
0x1800138f8  lea     rcx, [rbp+arg_8]; this
0x1800138fc  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180013901  mov     rbx, [rbp+arg_8]
0x180013905  mov     edi, eax
0x180013907  lea     rcx, [rbp+arg_8]
0x18001390b  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x180013913  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x180013918  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001391c  mov     [rbp+arg_8], rsi
0x180013920  test    edi, edi
0x180013922  js      short loc_180013960
0x180013924  xor     r9d, r9d; lpName
0x180013927  lea     edx, [rsi+2]; bManualReset
0x18001392a  xor     r8d, r8d; bInitialState
0x18001392d  xor     ecx, ecx; lpEventAttributes
0x18001392f  call    cs:__imp_CreateEventW
0x180013935  mov     rdx, rax
0x180013938  lea     rcx, [rbp+arg_8]
0x18001393c  call    ??4TAutoHandleNT@NCoreLibrary@@QEAAPEAXPEAX@Z; NCoreLibrary::TAutoHandleNT::operator=(void *)
0x180013941  mov     rsi, [rbp+arg_8]
0x180013945  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180013949  jnz     short loc_180013960
0x18001394b  call    cs:__imp_GetLastError
0x180013951  mov     edi, eax
0x180013953  test    eax, eax
0x180013955  jle     short loc_180013960
0x180013957  movzx   edi, ax
0x18001395a  or      edi, 80070000h
0x180013960  xor     eax, eax
0x180013962  xorps   xmm0, xmm0
0x180013965  mov     [rbp+var_10], rax
0x180013969  mov     [rbp+arg_10], rax
0x18001396d  movups  [rbp+var_20], xmm0
0x180013971  test    edi, edi
0x180013973  js      loc_180013A36
0x180013979  mov     dword ptr [rbp+var_10], eax
0x18001397c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180013980  mov     rcx, rsi
0x180013983  mov     rdx, rbx
0x180013986  cmovz   rcx, rax
0x18001398a  lea     rax, [rbp+arg_10]
0x18001398e  mov     [rsp+70h+var_28], rax
0x180013993  xor     r9d, r9d
0x180013996  lea     rax, [rbp+var_20]
0x18001399a  mov     qword ptr [rbp+var_20+8], rcx
0x18001399e  mov     [rsp+70h+var_30], rax
0x1800139a3  xor     r8d, r8d
0x1800139a6  lea     rax, ?DeviceQueryCallback@DeviceObject@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DeviceObject::DeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800139ad  mov     [rsp+70h+var_38], rax
0x1800139b2  lea     ecx, [r9+3]
0x1800139b6  mov     [rsp+70h+var_40], 0
0x1800139bf  mov     [rsp+70h+var_48], 0
0x1800139c7  mov     [rsp+70h+var_50], 0
0x1800139d0  call    cs:__imp_DevCreateObjectQueryFromId
0x1800139d6  mov     edi, eax
0x1800139d8  test    eax, eax
0x1800139da  js      short loc_180013A27
0x1800139dc  xor     eax, eax
0x1800139de  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800139e2  cmovz   rsi, rax
0x1800139e6  or      edi, 0FFFFFFFFh
0x1800139e9  mov     edx, edi; dwMilliseconds
0x1800139eb  mov     rcx, rsi; hHandle
0x1800139ee  call    cs:__imp_WaitForSingleObject
0x1800139f4  test    eax, eax
0x1800139f6  jnz     short loc_180013A07
0x1800139f8  mov     edi, dword ptr [rbp+var_10]
0x1800139fb  test    edi, edi
0x1800139fd  js      short loc_180013A27
0x1800139ff  mov     al, byte ptr [rbp+var_20]
0x180013a02  mov     [r14], al
0x180013a05  jmp     short loc_180013A27
0x180013a07  cmp     eax, edi
0x180013a09  jnz     short loc_180013A22
0x180013a0b  call    cs:__imp_GetLastError
0x180013a11  mov     edi, eax
0x180013a13  test    eax, eax
0x180013a15  jle     short loc_180013A27
0x180013a17  movzx   edi, ax
0x180013a1a  or      edi, 80070000h
0x180013a20  jmp     short loc_180013A27
0x180013a22  mov     edi, 8000FFFFh
0x180013a27  mov     rcx, [rbp+arg_10]
0x180013a2b  test    rcx, rcx
0x180013a2e  jz      short loc_180013A36
0x180013a30  call    cs:__imp_DevCloseObjectQuery
0x180013a36  lea     rcx, [rbp+arg_8]
0x180013a3a  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x180013a3f  mov     rdx, rbx; void *
0x180013a42  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180013a47  lea     r11, [rsp+70h+var_s0]
0x180013a4c  mov     eax, edi
0x180013a4e  mov     rbx, [r11+20h]
0x180013a52  mov     rsi, [r11+38h]
0x180013a56  mov     rsp, r11
0x180013a59  pop     r14
0x180013a5b  pop     rdi
0x180013a5c  pop     rbp
0x180013a5d  retn
```
