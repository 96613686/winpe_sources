# CWdsTptMgmtClient::InitializeEndpoint(_GUID,void * *)

- ea: `0x18001addc`
- end: `0x18001af43`
- name: `?InitializeEndpoint@CWdsTptMgmtClient@@AEAAKU_GUID@@PEAPEAX@Z`
- size: `359`
- prototype: `unsigned int __fastcall(CWdsTptMgmtClient *__hidden this, struct _GUID *__struct_ptr, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a8c4`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18001addc`
- `0x18001c3e0`
- `0x18001e9c2`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x18001aecc`
- `KERNEL32!GetComputerNameW` at `0x18001aecc`
- `KERNEL32!GetLastError` at `0x18001aedc`
- `KERNEL32!GetLastError` at `0x18001aedc`
- `WDSCSL!WdsClientSessionCreate` at `0x18001af03`
- `WDSCSL!WdsClientSessionCreate` at `0x18001af03`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001aeaf`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001aeaf`

## pseudocode

```c
__int64 __fastcall CWdsTptMgmtClient::InitializeEndpoint(CWdsTptMgmtClient *this, struct _GUID *a2, void **a3)
{
  __int64 v6; // r8
  WCHAR *v7; // rcx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  __int64 v10; // r8
  WCHAR v11; // ax
  WCHAR *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rbx
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  _BYTE v21[16]; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR Buffer[514]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD nSize; // [rsp+470h] [rbp+370h] BYREF

  nSize = 0;
  memset_0(&v23, 0, 0x410u);
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v21, (char *)this + 16);
  v6 = *((_QWORD *)this + 7);
  v7 = Buffer;
  v8 = (__int128)*a2;
  v9 = 512;
  v22[0] = 1052;
  v22[1] = 1;
  v22[2] = 1;
  v23 = v8;
  if ( !v6 )
  {
    nSize = 512;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      LastError = GetLastError();
      v13 = ElValidateWin32_14(LastError, v16, v17, 182);
      goto LABEL_10;
    }
LABEL_13:
    v14 = (unsigned int)WdsClientSessionCreate(0, 0, v22, a3);
    ElValidateWin32_14(v14, v18, v19, 188);
    goto LABEL_14;
  }
  v10 = v6 - (_QWORD)Buffer;
  do
  {
    if ( v9 == -2147483134 )
      break;
    v11 = *(WCHAR *)((char *)v7 + v10);
    if ( !v11 )
      break;
    *v7++ = v11;
    --v9;
  }
  while ( v9 );
  v12 = v7 - 1;
  if ( v9 )
    v12 = v7;
  *v12 = 0;
  if ( v9 )
    goto LABEL_13;
  v13 = WIN32_FROM_HRESULT(-2147024774);
LABEL_10:
  LODWORD(v14) = v13;
LABEL_14:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v21);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001addc  mov     [rsp-8+arg_8], rbx
0x18001ade1  mov     [rsp-8+arg_10], rsi
0x18001ade6  push    rbp
0x18001ade7  push    rdi
0x18001ade8  push    r14
0x18001adea  lea     rbp, [rsp-350h]
0x18001adf2  sub     rsp, 450h
0x18001adf9  mov     rsi, r8
0x18001adfc  mov     rbx, rdx
0x18001adff  mov     rdi, rcx
0x18001ae02  xor     r14d, r14d
0x18001ae05  xor     edx, edx; Val
0x18001ae07  mov     [rbp+360h+nSize], r14d
0x18001ae0e  mov     r8d, 410h; Size
0x18001ae14  lea     rcx, [rsp+460h+var_424]; void *
0x18001ae19  call    memset_0
0x18001ae1e  lea     rdx, [rdi+10h]
0x18001ae22  lea     rcx, [rsp+460h+var_440]
0x18001ae27  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18001ae2c  mov     r8, [rdi+38h]
0x18001ae30  lea     rcx, [rsp+460h+Buffer]; lpBuffer
0x18001ae35  movaps  xmm0, xmmword ptr [rbx]
0x18001ae38  mov     edx, 200h
0x18001ae3d  mov     [rsp+460h+var_430], 41Ch
0x18001ae45  mov     [rsp+460h+var_42C], 1
0x18001ae4d  mov     [rsp+460h+var_428], 1
0x18001ae55  movdqu  [rsp+460h+var_424], xmm0
0x18001ae5b  test    r8, r8
0x18001ae5e  jz      short loc_18001AEBF
0x18001ae60  lea     rax, [rsp+460h+Buffer]
0x18001ae65  sub     r8, rax
0x18001ae68  lea     rax, [rdx+7FFFFDFEh]
0x18001ae6f  test    rax, rax
0x18001ae72  jz      short loc_18001AE8B
0x18001ae74  movzx   eax, word ptr [r8+rcx]
0x18001ae79  test    ax, ax
0x18001ae7c  jz      short loc_18001AE8B
0x18001ae7e  mov     [rcx], ax
0x18001ae81  add     rcx, 2
0x18001ae85  sub     rdx, 1
0x18001ae89  jnz     short loc_18001AE68
0x18001ae8b  lea     rax, [rcx-2]
0x18001ae8f  test    rdx, rdx
0x18001ae92  cmovnz  rax, rcx
0x18001ae96  mov     [rax], r14w
0x18001ae9a  mov     rax, rdx
0x18001ae9d  neg     rax
0x18001aea0  sbb     ecx, ecx
0x18001aea2  not     ecx
0x18001aea4  and     ecx, 8007007Ah
0x18001aeaa  test    rdx, rdx
0x18001aead  jnz     short loc_18001AEF7
0x18001aeaf  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001aeb6  nop     dword ptr [rax+rax+00h]
0x18001aebb  mov     ebx, eax
0x18001aebd  jmp     short loc_18001AF1E
0x18001aebf  mov     [rbp+360h+nSize], edx
0x18001aec5  lea     rdx, [rbp+360h+nSize]; nSize
0x18001aecc  call    cs:__imp_GetComputerNameW
0x18001aed3  nop     dword ptr [rax+rax+00h]
0x18001aed8  test    eax, eax
0x18001aeda  jnz     short loc_18001AEF7
0x18001aedc  call    cs:__imp_GetLastError
0x18001aee3  nop     dword ptr [rax+rax+00h]
0x18001aee8  mov     ecx, eax
0x18001aeea  mov     r9d, 0B6h
0x18001aef0  call    ElValidateWin32_14
0x18001aef5  jmp     short loc_18001AEBB
0x18001aef7  mov     r9, rsi
0x18001aefa  lea     r8, [rsp+460h+var_430]
0x18001aeff  xor     edx, edx
0x18001af01  xor     ecx, ecx
0x18001af03  call    cs:__imp_WdsClientSessionCreate
0x18001af0a  nop     dword ptr [rax+rax+00h]
0x18001af0f  mov     ecx, eax
0x18001af11  mov     r9d, 0BCh
0x18001af17  mov     ebx, eax
0x18001af19  call    ElValidateWin32_14
0x18001af1e  lea     rcx, [rsp+460h+var_440]
0x18001af23  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18001af28  lea     r11, [rsp+460h+var_10]
0x18001af30  mov     eax, ebx
0x18001af32  mov     rbx, [r11+28h]
0x18001af36  mov     rsi, [r11+30h]
0x18001af3a  mov     rsp, r11
0x18001af3d  pop     r14
0x18001af3f  pop     rdi
0x18001af40  pop     rbp
0x18001af41  retn
```
