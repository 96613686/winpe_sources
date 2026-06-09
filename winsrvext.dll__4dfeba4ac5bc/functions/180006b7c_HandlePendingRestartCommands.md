# HandlePendingRestartCommands

- ea: `0x180006b7c`
- end: `0x180006d7f`
- name: `HandlePendingRestartCommands`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000acac`

## callees

- `0x18000587c`
- `0x180006b7c`
- `0x180007940`
- `0x18000a614`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x180006c99`
- `ntdll!NtSetValueKey` at `0x180006c99`
- `ntdll!RtlOpenCurrentUser` at `0x180006c00`
- `ntdll!RtlOpenCurrentUser` at `0x180006c00`
- `ntdll!NtSetInformationThread` at `0x180006be2`
- `ntdll!NtSetInformationThread` at `0x180006d10`
- `ntdll!NtSetInformationThread` at `0x180006be2`
- `ntdll!NtSetInformationThread` at `0x180006d10`
- `ntdll!RtlInitUnicodeString` at `0x180006c58`
- `ntdll!RtlInitUnicodeString` at `0x180006c58`
- `ntdll!NtClose` at `0x180006cad`
- `ntdll!NtClose` at `0x180006cee`
- `ntdll!NtClose` at `0x180006d38`
- `ntdll!NtClose` at `0x180006cad`
- `ntdll!NtClose` at `0x180006cee`
- `ntdll!NtClose` at `0x180006d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d47`

## pseudocode

```c
void __fastcall HandlePendingRestartCommands(int a1)
{
  _QWORD *v1; // rbx
  unsigned int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rax
  char v5; // r14
  int v6; // edx
  int v7; // r8d
  void *v8; // rcx
  HLOCAL v9; // rbx
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SourceString[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a1 >= 0 )
  {
    v1 = gprpi;
    v2 = 0;
    while ( v1 )
    {
      KeyHandle = 0;
      Handle = 0;
      ThreadInformation = 0;
      if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, v1 + 1, 8u) >= 0 )
      {
        if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) >= 0 )
        {
          if ( (int)CreateOrOpenKey(KeyHandle, v3, &Handle) >= 0 )
          {
            DestinationString = 0;
            RtlStringCchPrintfW(SourceString, 261, L"Application Restart #%d", v2++);
            RtlInitUnicodeString(&DestinationString, SourceString);
            v4 = -1;
            do
              ++v4;
            while ( *((_WORD *)v1 + v4 + 8) );
            v5 = NtSetValueKey(Handle, &DestinationString, 0, 1u, v1 + 2, 2 * v4 + 2);
            NtClose(Handle);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, (_DWORD)v1 + 16, v5);
            }
          }
          NtClose(KeyHandle);
        }
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      }
      v1 = (_QWORD *)*v1;
    }
  }
  while ( 1 )
  {
    v9 = gprpi;
    if ( !gprpi )
      break;
    v8 = (void *)*((_QWORD *)gprpi + 1);
    gprpi = *(HLOCAL *)gprpi;
    NtClose(v8);
    LocalFree(v9);
  }
}

```

## disassembly

```asm
0x180006b7c  push    rbp
0x180006b7e  push    rbx
0x180006b7f  push    rsi
0x180006b80  push    rdi
0x180006b81  push    r14
0x180006b83  push    r15
0x180006b85  lea     rbp, [rsp-188h]
0x180006b8d  sub     rsp, 288h
0x180006b94  mov     rax, cs:__security_cookie
0x180006b9b  xor     rax, rsp
0x180006b9e  mov     [rbp+1B0h+var_40], rax
0x180006ba5  xor     r15d, r15d
0x180006ba8  test    ecx, ecx
0x180006baa  js      loc_180006D53
0x180006bb0  mov     rbx, cs:gprpi
0x180006bb7  mov     esi, r15d
0x180006bba  jmp     loc_180006D1F
0x180006bbf  mov     edx, 5; ThreadInformationClass
0x180006bc4  mov     [rsp+2B0h+KeyHandle], r15
0x180006bc9  lea     r8, [rbx+8]; ThreadInformation
0x180006bcd  mov     [rsp+2B0h+Handle], r15
0x180006bd2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006bd9  mov     [rsp+2B0h+ThreadInformation], r15
0x180006bde  lea     r9d, [rdx+3]; ThreadInformationLength
0x180006be2  call    cs:__imp_NtSetInformationThread
0x180006be9  nop     dword ptr [rax+rax+00h]
0x180006bee  test    eax, eax
0x180006bf0  js      loc_180006D1C
0x180006bf6  lea     rdx, [rsp+2B0h+KeyHandle]; KeyHandle
0x180006bfb  mov     ecx, 2000000h; DesiredAccess
0x180006c00  call    cs:__imp_RtlOpenCurrentUser
0x180006c07  nop     dword ptr [rax+rax+00h]
0x180006c0c  test    eax, eax
0x180006c0e  js      loc_180006CFA
0x180006c14  mov     rcx, [rsp+2B0h+KeyHandle]
0x180006c19  lea     r8, [rsp+2B0h+Handle]
0x180006c1e  call    CreateOrOpenKey
0x180006c23  test    eax, eax
0x180006c25  js      loc_180006CE9
0x180006c2b  xorps   xmm0, xmm0
0x180006c2e  lea     r8, aApplicationRes; "Application Restart #%d"
0x180006c35  mov     r9d, esi
0x180006c38  lea     rcx, [rsp+2B0h+SourceString]
0x180006c3d  mov     edx, 105h
0x180006c42  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x180006c47  call    RtlStringCchPrintfW
0x180006c4c  lea     rdx, [rsp+2B0h+SourceString]; SourceString
0x180006c51  inc     esi
0x180006c53  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180006c58  call    cs:__imp_RtlInitUnicodeString
0x180006c5f  nop     dword ptr [rax+rax+00h]
0x180006c64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c68  lea     rdi, [rbx+10h]
0x180006c6c  inc     rax
0x180006c6f  cmp     [rdi+rax*2], r15w
0x180006c74  jnz     short loc_180006C6C
0x180006c76  mov     rcx, [rsp+2B0h+Handle]; KeyHandle
0x180006c7b  lea     eax, ds:2[rax*2]
0x180006c82  mov     [rsp+2B0h+DataSize], eax; DataSize
0x180006c86  lea     rdx, [rsp+2B0h+DestinationString]; ValueName
0x180006c8b  mov     r9d, 1; Type
0x180006c91  mov     [rsp+2B0h+Data], rdi; Data
0x180006c96  xor     r8d, r8d; TitleIndex
0x180006c99  call    cs:__imp_NtSetValueKey
0x180006ca0  nop     dword ptr [rax+rax+00h]
0x180006ca5  mov     rcx, [rsp+2B0h+Handle]; Handle
0x180006caa  mov     r14d, eax
0x180006cad  call    cs:__imp_NtClose
0x180006cb4  nop     dword ptr [rax+rax+00h]
0x180006cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc0  lea     rax, WPP_GLOBAL_Control
0x180006cc7  cmp     rcx, rax
0x180006cca  jz      short loc_180006CE9
0x180006ccc  test    byte ptr [rcx+1Ch], 1
0x180006cd0  jz      short loc_180006CE9
0x180006cd2  cmp     byte ptr [rcx+19h], 4
0x180006cd6  jb      short loc_180006CE9
0x180006cd8  mov     rcx, [rcx+10h]
0x180006cdc  mov     r9, rdi
0x180006cdf  mov     dword ptr [rsp+2B0h+Data], r14d
0x180006ce4  call    WPP_SF_SD
0x180006ce9  mov     rcx, [rsp+2B0h+KeyHandle]; Handle
0x180006cee  call    cs:__imp_NtClose
0x180006cf5  nop     dword ptr [rax+rax+00h]
0x180006cfa  mov     r9d, 8; ThreadInformationLength
0x180006d00  lea     r8, [rsp+2B0h+ThreadInformation]; ThreadInformation
0x180006d05  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006d0c  lea     edx, [r9-3]; ThreadInformationClass
0x180006d10  call    cs:__imp_NtSetInformationThread
0x180006d17  nop     dword ptr [rax+rax+00h]
0x180006d1c  mov     rbx, [rbx]
0x180006d1f  test    rbx, rbx
0x180006d22  jnz     loc_180006BBF
0x180006d28  jmp     short loc_180006D53
0x180006d2a  mov     rax, [rbx]
0x180006d2d  mov     rcx, [rbx+8]; Handle
0x180006d31  mov     cs:gprpi, rax
0x180006d38  call    cs:__imp_NtClose
0x180006d3f  nop     dword ptr [rax+rax+00h]
0x180006d44  mov     rcx, rbx; hMem
0x180006d47  call    cs:__imp_LocalFree
0x180006d4e  nop     dword ptr [rax+rax+00h]
0x180006d53  mov     rbx, cs:gprpi
0x180006d5a  test    rbx, rbx
0x180006d5d  jnz     short loc_180006D2A
0x180006d5f  mov     rcx, [rbp+1B0h+var_40]
0x180006d66  xor     rcx, rsp; StackCookie
0x180006d69  call    __security_check_cookie
0x180006d6e  add     rsp, 288h
0x180006d75  pop     r15
0x180006d77  pop     r14
0x180006d79  pop     rdi
0x180006d7a  pop     rsi
0x180006d7b  pop     rbx
0x180006d7c  pop     rbp
0x180006d7d  retn
```
