# CWdsSimpleDeviceController::DeleteDevice(IWdsDeviceControllerRequest *,ushort *)

- ea: `0x180005b10`
- end: `0x180005c19`
- name: `?DeleteDevice@CWdsSimpleDeviceController@@UEAAJPEAUIWdsDeviceControllerRequest@@PEAG@Z`
- size: `265`
- prototype: `int(CWdsSimpleDeviceController *__hidden this, struct IWdsDeviceControllerRequest *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005508`
- `0x180005b10`
- `0x180005dac`
- `0x180006dd8`
- `0x180008d44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005bb6`
- `KERNEL32!GetLastError` at `0x180005bb6`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180005ba6`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180005ba6`
- `KERNEL32!EnterCriticalSection` at `0x180005b3e`
- `KERNEL32!EnterCriticalSection` at `0x180005b3e`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::DeleteDevice(
        CWdsSimpleDeviceController *this,
        struct IWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  int Metadata; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  signed int v12; // eax
  char *v14; // [rsp+20h] [rbp-60h] BYREF
  int v15; // [rsp+28h] [rbp-58h]
  _QWORD v16[10]; // [rsp+30h] [rbp-50h] BYREF

  v5 = 0;
  v14 = (char *)this + 64;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v15 = 1;
  v16[0] = 0;
  v16[1] = 0;
  v16[3] = 0;
  v16[4] = 0;
  v16[6] = 0;
  v16[7] = 0;
  Metadata = CWdsSimpleDeviceController::GetMetadata(
               (CWdsSimpleDeviceController *)((char *)this - 8),
               a3,
               (struct CWdsMetadata *)v16);
  if ( (unsigned int)ElValidateWin32((unsigned int)Metadata, v7, v8, 786) )
  {
    if ( Metadata > 0 )
      Metadata = (unsigned __int16)Metadata | 0x80070000;
    v5 = Metadata;
  }
  else if ( !WritePrivateProfileSectionW(a3, 0, *((LPCWSTR *)this + 13)) )
  {
    LastError = GetLastError();
    v12 = ElValidateWin32(LastError, v10, v11, 796);
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    v5 = v12;
  }
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v16);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v14);
  return v5;
}

```

## disassembly

```asm
0x180005b10  mov     rax, rsp
0x180005b13  mov     [rax+8], rbx
0x180005b17  mov     [rax+10h], rsi
0x180005b1b  mov     [rax+18h], rdi
0x180005b1f  mov     [rax+20h], r14
0x180005b23  push    rbp
0x180005b24  mov     rbp, rsp
0x180005b27  sub     rsp, 80h
0x180005b2e  mov     rsi, rcx
0x180005b31  mov     r14, r8
0x180005b34  add     rcx, 40h ; '@'; lpCriticalSection
0x180005b38  xor     ebx, ebx
0x180005b3a  mov     [rbp+var_60], rcx
0x180005b3e  call    cs:__imp_EnterCriticalSection
0x180005b45  nop     dword ptr [rax+rax+00h]
0x180005b4a  lea     rcx, [rsi-8]; this
0x180005b4e  mov     [rbp+var_58], 1
0x180005b55  lea     r8, [rbp+var_50]; struct CWdsMetadata *
0x180005b59  mov     [rbp+var_50], rbx
0x180005b5d  mov     rdx, r14; unsigned __int16 *
0x180005b60  mov     [rbp+var_48], rbx
0x180005b64  mov     [rbp+var_38], rbx
0x180005b68  mov     [rbp+var_30], rbx
0x180005b6c  mov     [rbp+var_20], rbx
0x180005b70  mov     [rbp+var_18], rbx
0x180005b74  call    ?GetMetadata@CWdsSimpleDeviceController@@QEAAKPEBGPEAVCWdsMetadata@@@Z; CWdsSimpleDeviceController::GetMetadata(ushort const *,CWdsMetadata *)
0x180005b79  mov     r9d, 312h
0x180005b7f  mov     ecx, eax
0x180005b81  mov     edi, eax
0x180005b83  call    ElValidateWin32
0x180005b88  test    eax, eax
0x180005b8a  jz      short loc_180005B9D
0x180005b8c  test    edi, edi
0x180005b8e  jle     short loc_180005B99
0x180005b90  movzx   edi, di
0x180005b93  or      edi, 80070000h
0x180005b99  mov     ebx, edi
0x180005b9b  jmp     short loc_180005BE7
0x180005b9d  mov     r8, [rsi+68h]; lpFileName
0x180005ba1  xor     edx, edx; lpString
0x180005ba3  mov     rcx, r14; lpAppName
0x180005ba6  call    cs:__imp_WritePrivateProfileSectionW
0x180005bad  nop     dword ptr [rax+rax+00h]
0x180005bb2  test    eax, eax
0x180005bb4  jnz     short loc_180005BE7
0x180005bb6  call    cs:__imp_GetLastError
0x180005bbd  nop     dword ptr [rax+rax+00h]
0x180005bc2  mov     ecx, eax
0x180005bc4  mov     r9d, 31Ch
0x180005bca  call    ElValidateWin32
0x180005bcf  test    eax, eax
0x180005bd1  jle     short loc_180005BDB
0x180005bd3  movzx   eax, ax
0x180005bd6  or      eax, 80070000h
0x180005bdb  test    eax, eax
0x180005bdd  mov     ecx, 80004005h
0x180005be2  cmovns  eax, ecx
0x180005be5  mov     ebx, eax
0x180005be7  lea     rcx, [rbp+var_50]; this
0x180005beb  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005bf0  lea     rcx, [rbp+var_60]
0x180005bf4  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180005bf9  lea     r11, [rsp+80h+var_s0]
0x180005c01  mov     eax, ebx
0x180005c03  mov     rbx, [r11+10h]
0x180005c07  mov     rsi, [r11+18h]
0x180005c0b  mov     rdi, [r11+20h]
0x180005c0f  mov     r14, [r11+28h]
0x180005c13  mov     rsp, r11
0x180005c16  pop     rbp
0x180005c17  retn
```
