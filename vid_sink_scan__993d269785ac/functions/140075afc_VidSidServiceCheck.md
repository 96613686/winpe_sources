# VidSidServiceCheck

- ea: `0x140075afc`
- end: `0x140075c1d`
- name: `VidSidServiceCheck`
- size: `289`
- prototype: `__int64()`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140081948`
- `0x140081ad0`
- `0x140081b48`
- `0x140081bdc`
- `0x140081d68`
- `0x14008c17c`
- `0x14008c74c`
- `0x14009fe78`
- `0x1400aea40`
- `0x1400aec04`

## callees

- `0x140021650`
- `0x140021800`
- `0x140075a04`
- `0x140075afc`
- `0x140099efc`
- `0x140099fbc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140075bf1`
- `ntoskrnl!ZwClose` at `0x140075bf1`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140075b4f`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140075b4f`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140075b84`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140075bbf`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140075b84`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140075bbf`

## pseudocode

```c
__int64 VidSidServiceCheck()
{
  NTSTATUS v0; // ebx
  _BYTE v2[4]; // [rsp+20h] [rbp-19h] BYREF
  int v3; // [rsp+24h] [rbp-15h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-11h] BYREF
  _BYTE v5[80]; // [rsp+30h] [rbp-9h] BYREF

  TokenHandle = 0;
  v2[0] = 0;
  memset(v5, 0, 0x44u);
  v3 = 68;
  v0 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
  if ( v0 >= 0 )
  {
    v0 = VidSidInitializeVmCompute(v5, &v3);
    if ( v0 >= 0 )
    {
      v0 = RtlCheckTokenMembership(TokenHandle, v5, v2);
      if ( v0 >= 0 )
      {
        if ( v2[0] )
        {
LABEL_5:
          v0 = 0;
          goto LABEL_10;
        }
        v0 = VidSidpInitializeVmms(v5, &v3);
        if ( v0 >= 0 )
        {
          v0 = RtlCheckTokenMembership(TokenHandle, v5, v2);
          if ( v0 >= 0 )
          {
            if ( v2[0] )
              goto LABEL_5;
            v0 = (unsigned int)VidCurrentProcessIsAdmin() == 0 ? 0xC000000D : 0;
          }
        }
      }
    }
  }
LABEL_10:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140075afc  mov     [rsp-8+arg_0], rbx
0x140075b01  push    rbp
0x140075b02  lea     rbp, [rsp-57h]
0x140075b07  sub     rsp, 90h
0x140075b0e  mov     rax, cs:__security_cookie
0x140075b15  xor     rax, rsp
0x140075b18  mov     [rbp+57h+var_10], rax
0x140075b1c  mov     ebx, 44h ; 'D'
0x140075b21  mov     [rbp+57h+TokenHandle], 0
0x140075b29  mov     r8d, ebx; Size
0x140075b2c  mov     [rbp+57h+var_70], 0
0x140075b30  xor     edx, edx; Val
0x140075b32  lea     rcx, [rbp+57h+var_60]; void *
0x140075b36  call    memset
0x140075b3b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140075b3f  mov     [rbp+57h+var_6C], ebx
0x140075b42  lea     edx, [rbx-3Ch]; DesiredAccess
0x140075b45  mov     r8d, 200h; HandleAttributes
0x140075b4b  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140075b4f  call    cs:__imp_ZwOpenProcessTokenEx
0x140075b56  nop     dword ptr [rax+rax+00h]
0x140075b5b  mov     ebx, eax
0x140075b5d  test    eax, eax
0x140075b5f  js      loc_140075BE8
0x140075b65  lea     rdx, [rbp+57h+var_6C]
0x140075b69  lea     rcx, [rbp+57h+var_60]
0x140075b6d  call    VidSidInitializeVmCompute
0x140075b72  mov     ebx, eax
0x140075b74  test    eax, eax
0x140075b76  js      short loc_140075BE8
0x140075b78  mov     rcx, [rbp+57h+TokenHandle]
0x140075b7c  lea     r8, [rbp+57h+var_70]
0x140075b80  lea     rdx, [rbp+57h+var_60]
0x140075b84  call    cs:__imp_RtlCheckTokenMembership
0x140075b8b  nop     dword ptr [rax+rax+00h]
0x140075b90  mov     ebx, eax
0x140075b92  test    eax, eax
0x140075b94  js      short loc_140075BE8
0x140075b96  cmp     [rbp+57h+var_70], 0
0x140075b9a  jz      short loc_140075BA0
0x140075b9c  xor     ebx, ebx
0x140075b9e  jmp     short loc_140075BE8
0x140075ba0  lea     rdx, [rbp+57h+var_6C]
0x140075ba4  lea     rcx, [rbp+57h+var_60]
0x140075ba8  call    VidSidpInitializeVmms
0x140075bad  mov     ebx, eax
0x140075baf  test    eax, eax
0x140075bb1  js      short loc_140075BE8
0x140075bb3  mov     rcx, [rbp+57h+TokenHandle]
0x140075bb7  lea     r8, [rbp+57h+var_70]
0x140075bbb  lea     rdx, [rbp+57h+var_60]
0x140075bbf  call    cs:__imp_RtlCheckTokenMembership
0x140075bc6  nop     dword ptr [rax+rax+00h]
0x140075bcb  mov     ebx, eax
0x140075bcd  test    eax, eax
0x140075bcf  js      short loc_140075BE8
0x140075bd1  cmp     [rbp+57h+var_70], 0
0x140075bd5  jnz     short loc_140075B9C
0x140075bd7  call    VidCurrentProcessIsAdmin
0x140075bdc  neg     eax
0x140075bde  sbb     ebx, ebx
0x140075be0  not     ebx
0x140075be2  and     ebx, 0C000000Dh
0x140075be8  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140075bec  test    rcx, rcx
0x140075bef  jz      short loc_140075BFD
0x140075bf1  call    cs:__imp_ZwClose
0x140075bf8  nop     dword ptr [rax+rax+00h]
0x140075bfd  mov     eax, ebx
0x140075bff  mov     rcx, [rbp+57h+var_10]
0x140075c03  xor     rcx, rsp; StackCookie
0x140075c06  call    __security_check_cookie
0x140075c0b  mov     rbx, [rsp+90h+arg_0]
0x140075c13  add     rsp, 90h
0x140075c1a  pop     rbp
0x140075c1b  retn
```
