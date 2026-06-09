# sub_18005CBEC

- ea: `0x18005cbec`
- end: `0x18005cdb0`
- name: `sub_18005CBEC`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800519e0`

## callees

- `0x180056954`
- `0x18005cbec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005cd84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005cd98`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005cd84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005cd98`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005cc9b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005cc9b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005cc09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005cc09`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18005cd70`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18005cd70`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18005ccfe`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18005ccfe`

## pseudocode

```c
__int64 __fastcall sub_18005CBEC(__int64 a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rdi
  DWORD LastError; // eax
  __int64 v6; // rdx
  signed int v7; // eax
  int v8; // ebx
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  v2 = OpenSCManagerW(0, 0, 4u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = 0;
    if ( off_1800C0000 == (_UNKNOWN *)&off_1800C0000
      || (*((_BYTE *)off_1800C0000 + 28) & 4) == 0
      || *((_BYTE *)off_1800C0000 + 25) < 2u )
    {
      goto LABEL_7;
    }
    LastError = GetLastError();
    v6 = 26;
LABEL_6:
    sub_180056954(*((_QWORD *)off_1800C0000 + 2), v6, qword_1800AA170, LastError);
LABEL_7:
    v7 = GetLastError();
    v8 = v7;
    if ( v7 <= 0 )
      goto LABEL_23;
    v8 = (unsigned __int16)v7;
    goto LABEL_9;
  }
  v4 = OpenServiceW(v2, L"EventLog", 4u);
  if ( !v4 )
  {
    if ( off_1800C0000 == (_UNKNOWN *)&off_1800C0000
      || (*((_BYTE *)off_1800C0000 + 28) & 4) == 0
      || *((_BYTE *)off_1800C0000 + 25) < 2u )
    {
      goto LABEL_7;
    }
    LastError = GetLastError();
    v6 = 27;
    goto LABEL_6;
  }
  v8 = SubscribeServiceChangeNotifications(v4, 2, &sub_180052D30, a1, &v10);
  if ( v8 )
  {
    if ( off_1800C0000 != (_UNKNOWN *)&off_1800C0000
      && (*((_BYTE *)off_1800C0000 + 28) & 4) != 0
      && *((_BYTE *)off_1800C0000 + 25) >= 2u )
    {
      sub_180056954(*((_QWORD *)off_1800C0000 + 2), 28, qword_1800AA170, (unsigned int)v8);
    }
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8;
LABEL_9:
      v8 |= 0x80070000;
    }
  }
  else
  {
    v8 = 0;
    *(_QWORD *)(a1 + 136) = v10;
    v10 = 0;
  }
LABEL_23:
  if ( v10 )
    UnsubscribeServiceChangeNotifications();
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v3 )
    CloseServiceHandle(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005cbec  push    rbx
0x18005cbee  push    rbp
0x18005cbef  push    rsi
0x18005cbf0  push    rdi
0x18005cbf1  sub     rsp, 38h
0x18005cbf5  xor     edx, edx; lpDatabaseName
0x18005cbf7  mov     [rsp+58h+arg_8], 0
0x18005cc00  mov     rbp, rcx
0x18005cc03  xor     ecx, ecx; lpMachineName
0x18005cc05  lea     r8d, [rdx+4]; dwDesiredAccess
0x18005cc09  call    cs:OpenSCManagerW
0x18005cc10  nop     dword ptr [rax+rax+00h]
0x18005cc15  mov     rsi, rax
0x18005cc18  test    rax, rax
0x18005cc1b  jnz     short loc_18005CC8B
0x18005cc1d  xor     edi, edi
0x18005cc1f  mov     rdx, cs:off_1800C0000
0x18005cc26  lea     rcx, off_1800C0000
0x18005cc2d  cmp     rdx, rcx
0x18005cc30  jz      short loc_18005CC67
0x18005cc32  test    byte ptr [rdx+1Ch], 4
0x18005cc36  jz      short loc_18005CC67
0x18005cc38  cmp     byte ptr [rdx+19h], 2
0x18005cc3c  jb      short loc_18005CC67
0x18005cc3e  call    cs:GetLastError
0x18005cc45  nop     dword ptr [rax+rax+00h]
0x18005cc4a  lea     edx, [rsi+1Ah]
0x18005cc4d  mov     rcx, cs:off_1800C0000
0x18005cc54  lea     r8, qword_1800AA170
0x18005cc5b  mov     r9d, eax
0x18005cc5e  mov     rcx, [rcx+10h]
0x18005cc62  call    sub_180056954
0x18005cc67  call    cs:GetLastError
0x18005cc6e  nop     dword ptr [rax+rax+00h]
0x18005cc73  mov     ebx, eax
0x18005cc75  test    eax, eax
0x18005cc77  jle     loc_18005CD66
0x18005cc7d  movzx   ebx, ax
0x18005cc80  or      ebx, 80070000h
0x18005cc86  jmp     loc_18005CD66
0x18005cc8b  mov     r8d, 4; dwDesiredAccess
0x18005cc91  lea     rdx, ServiceName; "EventLog"
0x18005cc98  mov     rcx, rsi; hSCManager
0x18005cc9b  call    cs:OpenServiceW
0x18005cca2  nop     dword ptr [rax+rax+00h]
0x18005cca7  mov     rdi, rax
0x18005ccaa  test    rax, rax
0x18005ccad  jnz     short loc_18005CCE2
0x18005ccaf  mov     rdx, cs:off_1800C0000
0x18005ccb6  lea     rcx, off_1800C0000
0x18005ccbd  cmp     rdx, rcx
0x18005ccc0  jz      short loc_18005CC67
0x18005ccc2  test    byte ptr [rdx+1Ch], 4
0x18005ccc6  jz      short loc_18005CC67
0x18005ccc8  cmp     byte ptr [rdx+19h], 2
0x18005cccc  jb      short loc_18005CC67
0x18005ccce  call    cs:GetLastError
0x18005ccd5  nop     dword ptr [rax+rax+00h]
0x18005ccda  lea     edx, [rdi+1Bh]
0x18005ccdd  jmp     loc_18005CC4D
0x18005cce2  lea     rax, [rsp+58h+arg_8]
0x18005cce7  mov     r9, rbp
0x18005ccea  lea     r8, sub_180052D30
0x18005ccf1  mov     [rsp+58h+var_38], rax
0x18005ccf6  mov     edx, 2
0x18005ccfb  mov     rcx, rdi
0x18005ccfe  call    cs:SubscribeServiceChangeNotifications
0x18005cd05  nop     dword ptr [rax+rax+00h]
0x18005cd0a  mov     ebx, eax
0x18005cd0c  test    eax, eax
0x18005cd0e  jz      short loc_18005CD53
0x18005cd10  mov     rax, cs:off_1800C0000
0x18005cd17  lea     rcx, off_1800C0000
0x18005cd1e  cmp     rax, rcx
0x18005cd21  jz      short loc_18005CD47
0x18005cd23  test    byte ptr [rax+1Ch], 4
0x18005cd27  jz      short loc_18005CD47
0x18005cd29  cmp     byte ptr [rax+19h], 2
0x18005cd2d  jb      short loc_18005CD47
0x18005cd2f  mov     rcx, [rax+10h]
0x18005cd33  lea     r8, qword_1800AA170
0x18005cd3a  mov     edx, 1Ch
0x18005cd3f  mov     r9d, ebx
0x18005cd42  call    sub_180056954
0x18005cd47  test    ebx, ebx
0x18005cd49  jle     short loc_18005CD66
0x18005cd4b  movzx   ebx, bx
0x18005cd4e  jmp     loc_18005CC80
0x18005cd53  mov     rax, [rsp+58h+arg_8]
0x18005cd58  xor     ebx, ebx
0x18005cd5a  mov     [rbp+88h], rax
0x18005cd61  mov     [rsp+58h+arg_8], rbx
0x18005cd66  mov     rcx, [rsp+58h+arg_8]
0x18005cd6b  test    rcx, rcx
0x18005cd6e  jz      short loc_18005CD7C
0x18005cd70  call    cs:UnsubscribeServiceChangeNotifications
0x18005cd77  nop     dword ptr [rax+rax+00h]
0x18005cd7c  test    rdi, rdi
0x18005cd7f  jz      short loc_18005CD90
0x18005cd81  mov     rcx, rdi; hSCObject
0x18005cd84  call    cs:CloseServiceHandle
0x18005cd8b  nop     dword ptr [rax+rax+00h]
0x18005cd90  test    rsi, rsi
0x18005cd93  jz      short loc_18005CDA4
0x18005cd95  mov     rcx, rsi; hSCObject
0x18005cd98  call    cs:CloseServiceHandle
0x18005cd9f  nop     dword ptr [rax+rax+00h]
0x18005cda4  mov     eax, ebx
0x18005cda6  add     rsp, 38h
0x18005cdaa  pop     rdi
0x18005cdab  pop     rsi
0x18005cdac  pop     rbp
0x18005cdad  pop     rbx
0x18005cdae  retn
```
