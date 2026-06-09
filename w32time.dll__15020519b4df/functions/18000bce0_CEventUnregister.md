# CEventUnregister

- ea: `0x18000bce0`
- end: `0x18000bdcd`
- name: `CEventUnregister`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000bc88`

## callees

- `0x18000bce0`
- `0x18000bf68`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000bd93`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000bd93`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bd67`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bd67`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bdb5`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bdb5`
- `ntdll!RtlEnterCriticalSection` at `0x18000bd4f`
- `ntdll!RtlEnterCriticalSection` at `0x18000bd4f`

## pseudocode

```c
__int64 CEventUnregister()
{
  unsigned int v0; // ebx
  PVOID v2; // rax
  void *v3; // rdi
  _BYTE Buffer[56]; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v5; // [rsp+58h] [rbp-30h]

  if ( byte_1800A5340 )
  {
    memset_0(Buffer, 0, 0x48u);
    v5 = _W32TimeRegistrationHandle;
    RtlEnterCriticalSection(&stru_1800A52B0);
    v2 = RtlLookupElementGenericTableAvl(&Table, Buffer);
    v3 = v2;
    if ( v2 )
    {
      v0 = deinitEventList(v2);
      if ( v0 )
      {
LABEL_8:
        RtlLeaveCriticalSection(&stru_1800A52B0);
        return v0;
      }
      if ( RtlDeleteElementGenericTableAvl(&Table, v3) )
      {
        _W32TimeRegistrationHandle = 0;
        goto LABEL_8;
      }
    }
    v0 = 6;
    goto LABEL_8;
  }
  return 6;
}

```

## disassembly

```asm
0x18000bce0  mov     [rsp+arg_0], rbx
0x18000bce5  push    rdi
0x18000bce6  sub     rsp, 80h
0x18000bced  mov     rax, cs:__security_cookie
0x18000bcf4  xor     rax, rsp
0x18000bcf7  mov     [rsp+88h+var_18], rax
0x18000bcfc  mov     al, cs:byte_1800A5340
0x18000bd02  test    al, al
0x18000bd04  jnz     short loc_18000BD2C
0x18000bd06  mov     ebx, 6
0x18000bd0b  mov     eax, ebx
0x18000bd0d  mov     rcx, [rsp+88h+var_18]
0x18000bd12  xor     rcx, rsp; StackCookie
0x18000bd15  call    __security_check_cookie
0x18000bd1a  mov     rbx, [rsp+88h+arg_0]
0x18000bd22  add     rsp, 80h
0x18000bd29  pop     rdi
0x18000bd2a  retn
0x18000bd2c  xor     edx, edx; Val
0x18000bd2e  lea     rcx, [rsp+88h+Buffer]; void *
0x18000bd33  lea     r8d, [rdx+48h]; Size
0x18000bd37  call    memset_0
0x18000bd3c  mov     rax, cs:?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000bd43  lea     rcx, stru_1800A52B0; CriticalSection
0x18000bd4a  mov     [rsp+88h+var_30], rax
0x18000bd4f  call    cs:__imp_RtlEnterCriticalSection
0x18000bd56  nop     dword ptr [rax+rax+00h]
0x18000bd5b  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18000bd60  lea     rcx, Table; Table
0x18000bd67  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000bd6e  nop     dword ptr [rax+rax+00h]
0x18000bd73  mov     rdi, rax
0x18000bd76  test    rax, rax
0x18000bd79  jz      short loc_18000BDC6
0x18000bd7b  mov     rcx, rax
0x18000bd7e  call    deinitEventList
0x18000bd83  mov     ebx, eax
0x18000bd85  test    eax, eax
0x18000bd87  jnz     short loc_18000BDAE
0x18000bd89  mov     rdx, rdi; Buffer
0x18000bd8c  lea     rcx, Table; Table
0x18000bd93  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000bd9a  nop     dword ptr [rax+rax+00h]
0x18000bd9f  test    al, al
0x18000bda1  jz      short loc_18000BDC6
0x18000bda3  mov     cs:?_W32TimeRegistrationHandle@@3_KA, 0; unsigned __int64 _W32TimeRegistrationHandle
0x18000bdae  lea     rcx, stru_1800A52B0; CriticalSection
0x18000bdb5  call    cs:__imp_RtlLeaveCriticalSection
0x18000bdbc  nop     dword ptr [rax+rax+00h]
0x18000bdc1  jmp     loc_18000BD0B
0x18000bdc6  mov     ebx, 6
0x18000bdcb  jmp     short loc_18000BDAE
```
