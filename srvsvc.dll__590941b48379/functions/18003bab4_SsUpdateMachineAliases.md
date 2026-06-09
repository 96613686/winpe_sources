# SsUpdateMachineAliases

- ea: `0x18003bab4`
- end: `0x18003bc24`
- name: `SsUpdateMachineAliases`
- size: `368`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009470`
- `0x180009a20`
- `0x18002f0fc`
- `0x18002f8b8`

## callees

- `0x180008de0`
- `0x18001deb0`
- `0x18001e80c`
- `0x18003b860`
- `0x18003bab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbfb`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003bb8f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003bb8f`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003bbe8`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003bbe8`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003bbf2`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003bbf2`

## pseudocode

```c
__int64 __fastcall SsUpdateMachineAliases(HANDLE FileHandle)
{
  char *v2; // rax
  __int64 v3; // rcx
  _BYTE *v4; // rbx
  NTSTATUS LsaHandleAndPackageId; // edi
  ULONG AuthenticationPackage; // [rsp+48h] [rbp-69h] BYREF
  int ProtocolStatus; // [rsp+4Ch] [rbp-65h] BYREF
  HANDLE LsaHandle; // [rsp+50h] [rbp-61h] BYREF
  ULONG ReturnBufferLength; // [rsp+58h] [rbp-59h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int16 hMem[48]; // [rsp+68h] [rbp-49h] BYREF

  Buffer = 0;
  LsaHandle = 0;
  AuthenticationPackage = 0;
  ProtocolStatus = -1073741823;
  ReturnBufferLength = 0;
  memset_0(hMem, 0, sizeof(hMem));
  v2 = (char *)LocalAlloc(0x40u, 0x18u);
  v4 = v2;
  if ( v2 )
  {
    *(_OWORD *)(v2 + 8) = 0;
    *(_DWORD *)v2 = 13;
    *((_DWORD *)v2 + 1) = 4;
    *((_QWORD *)v2 + 2) = v2 + 24;
    LsaHandleAndPackageId = GetLsaHandleAndPackageId(v3, &LsaHandle, &AuthenticationPackage);
    if ( LsaHandleAndPackageId >= 0 )
    {
      LsaHandleAndPackageId = LsaCallAuthenticationPackage(
                                LsaHandle,
                                AuthenticationPackage,
                                v4,
                                0x18u,
                                &Buffer,
                                &ReturnBufferLength,
                                &ProtocolStatus);
      if ( LsaHandleAndPackageId >= 0 )
      {
        if ( ProtocolStatus >= 0 && (v4[4] & 4) != 0 )
        {
          memset_0(hMem, 0, sizeof(hMem));
          *(_OWORD *)hMem = *(_OWORD *)((char *)Buffer + 8);
          SsServerFsControlCommon(FileHandle, 0x146054u, hMem, 0, 0);
        }
        if ( Buffer )
          LsaFreeReturnBuffer(Buffer);
      }
      LsaDeregisterLogonProcess(LsaHandle);
    }
    LocalFree(v4);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)LsaHandleAndPackageId;
}

```

## disassembly

```asm
0x18003bab4  mov     rax, rsp
0x18003bab7  push    rbp
0x18003bab8  push    rbx
0x18003bab9  push    rdi
0x18003baba  push    r14
0x18003babc  lea     rbp, [rax-5Fh]
0x18003bac0  sub     rsp, 0E8h
0x18003bac7  movaps  xmmword ptr [rax-38h], xmm6
0x18003bacb  mov     rax, cs:__security_cookie
0x18003bad2  xor     rax, rsp
0x18003bad5  mov     [rbp+57h+var_40], rax
0x18003bad9  xor     edx, edx; Val
0x18003badb  mov     [rbp+57h+Buffer], 0
0x18003bae3  mov     r14, rcx
0x18003bae6  mov     [rbp+57h+LsaHandle], 0
0x18003baee  lea     rcx, [rbp+57h+hMem]; void *
0x18003baf2  mov     [rbp+57h+AuthenticationPackage], 0
0x18003baf9  mov     [rbp+57h+ProtocolStatus], 0C0000001h
0x18003bb00  xorps   xmm6, xmm6
0x18003bb03  lea     r8d, [rdx+60h]; Size
0x18003bb07  mov     [rbp+57h+var_B0], 0
0x18003bb0e  call    memset_0
0x18003bb13  mov     edx, 18h; uBytes
0x18003bb18  lea     ecx, [rdx+28h]; uFlags
0x18003bb1b  call    cs:__imp_LocalAlloc
0x18003bb21  mov     rbx, rax
0x18003bb24  test    rax, rax
0x18003bb27  jnz     short loc_18003BB33
0x18003bb29  mov     edi, 0C0000017h
0x18003bb2e  jmp     loc_18003BC01
0x18003bb33  movdqu  xmmword ptr [rax+8], xmm6
0x18003bb38  mov     dword ptr [rax], 0Dh
0x18003bb3e  lea     r8, [rbp+57h+AuthenticationPackage]
0x18003bb42  mov     dword ptr [rax+4], 4
0x18003bb49  lea     rdx, [rbp+57h+LsaHandle]
0x18003bb4d  add     rax, 18h
0x18003bb51  mov     [rbx+10h], rax
0x18003bb55  call    GetLsaHandleAndPackageId
0x18003bb5a  mov     edi, eax
0x18003bb5c  test    eax, eax
0x18003bb5e  js      loc_18003BBF8
0x18003bb64  mov     edx, [rbp+57h+AuthenticationPackage]; AuthenticationPackage
0x18003bb67  lea     rax, [rbp+57h+ProtocolStatus]
0x18003bb6b  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x18003bb6f  mov     r9d, 18h; SubmitBufferLength
0x18003bb75  mov     [rsp+30h], rax; ProtocolStatus
0x18003bb7a  mov     r8, rbx; ProtocolSubmitBuffer
0x18003bb7d  lea     rax, [rbp+57h+var_B0]
0x18003bb81  mov     [rsp+100h+ReturnBufferLength], rax; ReturnBufferLength
0x18003bb86  lea     rax, [rbp+57h+Buffer]
0x18003bb8a  mov     [rsp+100h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18003bb8f  call    cs:__imp_LsaCallAuthenticationPackage
0x18003bb95  mov     edi, eax
0x18003bb97  test    eax, eax
0x18003bb99  js      short loc_18003BBEE
0x18003bb9b  cmp     [rbp+57h+ProtocolStatus], 0
0x18003bb9f  jl      short loc_18003BBDF
0x18003bba1  test    byte ptr [rbx+4], 4
0x18003bba5  jz      short loc_18003BBDF
0x18003bba7  xor     edx, edx; Val
0x18003bba9  lea     rcx, [rbp+57h+hMem]; void *
0x18003bbad  lea     r8d, [rdx+60h]; Size
0x18003bbb1  call    memset_0
0x18003bbb6  mov     rax, [rbp+57h+Buffer]
0x18003bbba  lea     r8, [rbp+57h+hMem]; hMem
0x18003bbbe  xor     r9d, r9d; OutputBuffer
0x18003bbc1  mov     dword ptr [rsp+100h+ProtocolReturnBuffer], 0; ULONG
0x18003bbc9  mov     edx, 146054h; FsControlCode
0x18003bbce  mov     rcx, r14; FileHandle
0x18003bbd1  movups  xmm0, xmmword ptr [rax+8]
0x18003bbd5  movdqu  xmmword ptr [rbp+57h+hMem], xmm0
0x18003bbda  call    SsServerFsControlCommon
0x18003bbdf  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18003bbe3  test    rcx, rcx
0x18003bbe6  jz      short loc_18003BBEE
0x18003bbe8  call    cs:__imp_LsaFreeReturnBuffer
0x18003bbee  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x18003bbf2  call    cs:__imp_LsaDeregisterLogonProcess
0x18003bbf8  mov     rcx, rbx; hMem
0x18003bbfb  call    cs:__imp_LocalFree
0x18003bc01  mov     eax, edi
0x18003bc03  mov     rcx, [rbp+57h+var_40]
0x18003bc07  xor     rcx, rsp; StackCookie
0x18003bc0a  call    __security_check_cookie
0x18003bc0f  movaps  xmm6, [rsp+100h+var_38+8]
0x18003bc17  add     rsp, 0E8h
0x18003bc1e  pop     r14
0x18003bc20  pop     rdi
0x18003bc21  pop     rbx
0x18003bc22  pop     rbp
0x18003bc23  retn
```
