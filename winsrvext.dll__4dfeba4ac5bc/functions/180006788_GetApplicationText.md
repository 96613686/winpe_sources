# GetApplicationText

- ea: `0x180006788`
- end: `0x180006890`
- name: `GetApplicationText`
- size: `264`
- prototype: `int __fastcall(HWND, void *, WCHAR *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005b70`

## callees

- `0x180006788`

## import_xrefs

- `ntdll!NtOpenThread` at `0x180006828`
- `ntdll!NtOpenThread` at `0x180006828`
- `ntdll!NtClose` at `0x180006876`
- `ntdll!NtClose` at `0x180006876`
- `win32u!NtUserQueryWindow` at `0x1800067ee`
- `win32u!NtUserQueryWindow` at `0x1800067ee`
- `win32u!NtUserQueryInformationThread` at `0x180006856`
- `win32u!NtUserQueryInformationThread` at `0x180006856`
- `USER32!GetWindowTextW` at `0x1800067c6`
- `USER32!GetWindowTextW` at `0x1800067c6`

## pseudocode

```c
int __fastcall GetApplicationText(HWND a1, void *a2, WCHAR *a3, int a4)
{
  NTSTATUS v8; // eax
  __int64 v9; // rax
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+B0h] [rbp+48h] BYREF

  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ClientId = 0;
  GetWindowTextW(a1, a3, a4);
  if ( !*a3 )
  {
    if ( !a2 )
    {
      ClientId.UniqueProcess = 0;
      ObjectAttributes.Length = 48;
      ClientId.UniqueThread = (HANDLE)NtUserQueryWindow(a1, 2);
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = NtOpenThread(&ThreadHandle, 0x40u, &ObjectAttributes, &ClientId);
      a2 = ThreadHandle;
      if ( v8 < 0 || !ThreadHandle )
      {
        *a3 = 0;
        goto LABEL_8;
      }
    }
    NtUserQueryInformationThread(a2, 2, a3, (unsigned int)(2 * a4));
  }
  a2 = ThreadHandle;
LABEL_8:
  v9 = (unsigned int)(a4 - 1);
  a3[v9] = 0;
  if ( a2 )
    LODWORD(v9) = NtClose(a2);
  return v9;
}

```

## disassembly

```asm
0x180006788  push    rbp
0x18000678a  push    rbx
0x18000678b  push    rsi
0x18000678c  push    rdi
0x18000678d  push    r14
0x18000678f  push    r15
0x180006791  mov     rbp, rsp
0x180006794  sub     rsp, 68h
0x180006798  xorps   xmm0, xmm0
0x18000679b  mov     rdi, r8
0x18000679e  mov     rbx, rdx
0x1800067a1  xor     r15d, r15d
0x1800067a4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800067a8  mov     rdx, rdi; lpString
0x1800067ab  mov     [rbp+ThreadHandle], r15
0x1800067af  xor     eax, eax
0x1800067b1  mov     r8d, r9d; nMaxCount
0x1800067b4  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800067b8  mov     esi, r9d
0x1800067bb  mov     r14, rcx
0x1800067be  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800067c2  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x1800067c6  call    cs:__imp_GetWindowTextW
0x1800067cd  nop     dword ptr [rax+rax+00h]
0x1800067d2  cmp     [rdi], r15w
0x1800067d6  jnz     loc_180006862
0x1800067dc  test    rbx, rbx
0x1800067df  jnz     short loc_180006847
0x1800067e1  xorps   xmm0, xmm0
0x1800067e4  lea     edx, [rbx+2]
0x1800067e7  mov     rcx, r14
0x1800067ea  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x1800067ee  call    cs:__imp_NtUserQueryWindow
0x1800067f5  nop     dword ptr [rax+rax+00h]
0x1800067fa  xorps   xmm0, xmm0
0x1800067fd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180006804  lea     r9, [rbp+ClientId]; ClientId
0x180006808  mov     [rbp+ClientId.UniqueThread], rax
0x18000680c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180006810  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180006814  lea     edx, [rbx+40h]; DesiredAccess
0x180006817  mov     [rbp+ObjectAttributes.Attributes], r15d
0x18000681b  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x18000681f  mov     [rbp+ObjectAttributes.ObjectName], r15
0x180006823  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180006828  call    cs:__imp_NtOpenThread
0x18000682f  nop     dword ptr [rax+rax+00h]
0x180006834  mov     rbx, [rbp+ThreadHandle]
0x180006838  test    eax, eax
0x18000683a  js      short loc_180006841
0x18000683c  test    rbx, rbx
0x18000683f  jnz     short loc_180006847
0x180006841  mov     [rdi], r15w
0x180006845  jmp     short loc_180006866
0x180006847  lea     r9d, [rsi+rsi]
0x18000684b  mov     r8, rdi
0x18000684e  mov     edx, 2
0x180006853  mov     rcx, rbx
0x180006856  call    cs:__imp_NtUserQueryInformationThread
0x18000685d  nop     dword ptr [rax+rax+00h]
0x180006862  mov     rbx, [rbp+ThreadHandle]
0x180006866  lea     eax, [rsi-1]
0x180006869  mov     [rdi+rax*2], r15w
0x18000686e  test    rbx, rbx
0x180006871  jz      short loc_180006882
0x180006873  mov     rcx, rbx; Handle
0x180006876  call    cs:__imp_NtClose
0x18000687d  nop     dword ptr [rax+rax+00h]
0x180006882  add     rsp, 68h
0x180006886  pop     r15
0x180006888  pop     r14
0x18000688a  pop     rdi
0x18000688b  pop     rsi
0x18000688c  pop     rbx
0x18000688d  pop     rbp
0x18000688e  retn
```
