# CollectorService::WaitForInit(void)

- ea: `0x180005d7c`
- end: `0x180005e57`
- name: `?WaitForInit@CollectorService@@AEAAXXZ`
- size: `219`
- prototype: `void __fastcall(CollectorService *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003f08`
- `0x1800042d0`
- `0x180004434`
- `0x180004608`
- `0x180004760`
- `0x180004b80`
- `0x1800052cc`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180005d7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005da8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005da8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005d96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005d96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e50`

## string_xrefs

- `0x180005dfb`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
void __fastcall CollectorService::WaitForInit(CollectorService *this)
{
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v3; // [rsp+28h] [rbp-40h]
  const char *v4; // [rsp+30h] [rbp-38h]
  __int64 v5; // [rsp+38h] [rbp-30h]
  __int64 v6; // [rsp+40h] [rbp-28h]
  int v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+4Ch] [rbp-1Ch]
  int v9; // [rsp+50h] [rbp-18h]

  if ( *((_DWORD *)this + 26) == 1 )
    WaitForSingleObject(*((HANDLE *)this + 14), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 26) == 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 1115);
    }
    v3 = 0;
    v4 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v5 = 0;
    v6 = 0;
    v7 = 1115;
    v8 = -1;
    v9 = 196;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x180005d7c  mov     [rsp+arg_8], rbx
0x180005d81  push    rdi
0x180005d82  sub     rsp, 60h
0x180005d86  mov     rbx, rcx
0x180005d89  cmp     dword ptr [rcx+68h], 1
0x180005d8d  jnz     short loc_180005D9C
0x180005d8f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005d92  mov     rcx, [rcx+70h]; hHandle
0x180005d96  call    cs:__imp_WaitForSingleObject
0x180005d9c  lea     rdi, [rbx+40h]
0x180005da0  mov     [rsp+68h+arg_0], rdi
0x180005da5  mov     rcx, rdi; lpCriticalSection
0x180005da8  call    cs:__imp_EnterCriticalSection
0x180005dae  nop
0x180005daf  cmp     dword ptr [rbx+68h], 3
0x180005db3  jnz     loc_180005E43
0x180005db9  lea     rax, WPP_GLOBAL_Control
0x180005dc0  mov     ebx, 45Bh
0x180005dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dcc  cmp     rcx, rax
0x180005dcf  jz      short loc_180005DF5
0x180005dd1  test    byte ptr [rcx+1Ch], 10h
0x180005dd5  jz      short loc_180005DF5
0x180005dd7  cmp     byte ptr [rcx+19h], 2
0x180005ddb  jb      short loc_180005DF5
0x180005ddd  mov     edx, 0Ah
0x180005de2  mov     r9d, ebx
0x180005de5  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180005dec  mov     rcx, [rcx+10h]
0x180005df0  call    WPP_SF_D
0x180005df5  xor     ecx, ecx
0x180005df7  mov     [rsp+68h+var_40], cl
0x180005dfb  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180005e02  mov     [rsp+68h+var_38], rax
0x180005e07  mov     [rsp+68h+var_30], rcx
0x180005e0c  mov     [rsp+68h+var_28], rcx
0x180005e11  mov     [rsp+68h+var_20], ebx
0x180005e15  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x180005e1d  mov     [rsp+68h+var_18], 0C4h
0x180005e25  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180005e2c  mov     [rsp+68h+pExceptionObject], rax
0x180005e31  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180005e38  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180005e3d  call    _CxxThrowException_0
0x180005e43  mov     rcx, rdi
0x180005e46  mov     rbx, [rsp+68h+arg_8]
0x180005e4b  add     rsp, 60h
0x180005e4f  pop     rdi
0x180005e50  jmp     cs:__imp_LeaveCriticalSection
```
