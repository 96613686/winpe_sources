# CWcnService::NotifyStatus(ulong)

- ea: `0x180003ad0`
- end: `0x180003b91`
- name: `?NotifyStatus@CWcnService@@AEAAXK@Z`
- size: `193`
- prototype: `void __fastcall(CWcnService *this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003288`
- `0x180004630`

## callees

- `0x180003ad0`
- `0x180005088`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003b74`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b34`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b11`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b11`

## pseudocode

```c
void __fastcall CWcnService::NotifyStatus(CWcnService *this, int a2)
{
  int v3; // eax
  int v4; // ecx
  int v5; // edi
  unsigned int Indent; // eax
  char v7; // r10

  *((_DWORD *)this + 3) = a2;
  if ( a2 == 4 )
  {
    *((_DWORD *)this + 7) = 0;
    v3 = 5;
    v4 = 0;
  }
  else
  {
    ++*((_DWORD *)this + 7);
    v4 = 1000;
    v3 = 0;
  }
  *((_DWORD *)this + 8) = v4;
  v5 = 0;
  *((_DWORD *)this + 4) = v3;
  do
  {
    if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, (LPSERVICE_STATUS)((char *)this + 8)) )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      GetLastError();
      Indent = (unsigned int)GetIndent(0);
      WPP_SF_sld(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids,
        Indent,
        v7,
        v5 + 1);
    }
    Sleep(0x1F4u);
    ++v5;
  }
  while ( v5 < 3 );
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp+arg_0], rbx
0x180003ad5  mov     [rsp+arg_8], rsi
0x180003ada  push    rdi
0x180003adb  sub     rsp, 30h
0x180003adf  mov     [rcx+0Ch], edx
0x180003ae2  mov     rbx, rcx
0x180003ae5  cmp     edx, 4
0x180003ae8  jnz     short loc_180003AF8
0x180003aea  mov     dword ptr [rcx+1Ch], 0
0x180003af1  lea     eax, [rdx+1]
0x180003af4  xor     ecx, ecx
0x180003af6  jmp     short loc_180003B02
0x180003af8  inc     dword ptr [rcx+1Ch]
0x180003afb  mov     ecx, 3E8h
0x180003b00  xor     eax, eax
0x180003b02  mov     [rbx+20h], ecx
0x180003b05  xor     edi, edi
0x180003b07  mov     [rbx+10h], eax
0x180003b0a  mov     rcx, [rbx]; hServiceStatus
0x180003b0d  lea     rdx, [rbx+8]; lpServiceStatus
0x180003b11  call    cs:__imp_SetServiceStatus
0x180003b17  test    eax, eax
0x180003b19  jnz     short loc_180003B81
0x180003b1b  mov     rax, cs:WPP_GLOBAL_Control
0x180003b22  lea     rcx, WPP_GLOBAL_Control
0x180003b29  cmp     rax, rcx
0x180003b2c  jz      short loc_180003B6F
0x180003b2e  cmp     byte ptr [rax+19h], 2
0x180003b32  jb      short loc_180003B6F
0x180003b34  call    cs:__imp_GetLastError
0x180003b3a  xor     ecx, ecx; int
0x180003b3c  mov     r10d, eax
0x180003b3f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003b44  lea     ecx, [rdi+1]
0x180003b47  mov     edx, 20h ; ' '
0x180003b4c  mov     [rsp+38h+var_10], ecx
0x180003b50  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b5e  mov     r9, rax
0x180003b61  mov     [rsp+38h+var_18], r10d
0x180003b66  mov     rcx, [rcx+10h]
0x180003b6a  call    WPP_SF_sld
0x180003b6f  mov     ecx, 1F4h; dwMilliseconds
0x180003b74  call    cs:__imp_Sleep
0x180003b7a  inc     edi
0x180003b7c  cmp     edi, 3
0x180003b7f  jl      short loc_180003B0A
0x180003b81  mov     rbx, [rsp+38h+arg_0]
0x180003b86  mov     rsi, [rsp+38h+arg_8]
0x180003b8b  add     rsp, 30h
0x180003b8f  pop     rdi
0x180003b90  retn
```
