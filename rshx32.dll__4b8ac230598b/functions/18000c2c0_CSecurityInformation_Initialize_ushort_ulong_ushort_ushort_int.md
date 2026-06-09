# CSecurityInformation::Initialize(ushort *,ulong,ushort *,ushort *,int)

- ea: `0x18000c2c0`
- end: `0x18000c351`
- name: `?Initialize@CSecurityInformation@@UEAAJPEAGK00H@Z`
- size: `145`
- prototype: `__int64 __fastcall(CSecurityInformation *this, unsigned __int16 *, int, unsigned __int16 *, unsigned __int16 *Buffer, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007390`
- `0x180008530`

## callees

- `0x18000c2c0`

## import_xrefs

- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000c30b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000c30b`
- `DSROLE!DsRoleFreeMemory` at `0x18000c32a`
- `DSROLE!DsRoleFreeMemory` at `0x18000c32a`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::Initialize(
        CSecurityInformation *this,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *Buffer,
        int a6)
{
  unsigned __int16 *v6; // rax
  BOOL v8; // edi
  __int64 result; // rax

  v6 = Buffer;
  if ( !Buffer || *((_QWORD *)this + 10) || !a2 )
    return 2147500035LL;
  *((_QWORD *)this + 7) = a2;
  v8 = 1;
  *((_DWORD *)this + 16) = a3;
  *((_QWORD *)this + 9) = a4;
  *((_QWORD *)this + 10) = v6;
  Buffer = 0;
  DsRoleGetPrimaryDomainInformation(a4, DsRolePrimaryDomainInfoBasic, (PBYTE *)&Buffer);
  if ( Buffer )
  {
    v8 = (*(_DWORD *)Buffer & 0xFFFFFFFD) == 0;
    DsRoleFreeMemory(Buffer);
  }
  *((_DWORD *)this + 77) = a6;
  result = 0;
  *((_DWORD *)this + 26) = v8;
  return result;
}

```

## disassembly

```asm
0x18000c2c0  mov     [rsp+arg_0], rbx
0x18000c2c5  push    rdi
0x18000c2c6  sub     rsp, 20h
0x18000c2ca  mov     rax, [rsp+28h+Buffer]
0x18000c2cf  mov     rbx, rcx
0x18000c2d2  test    rax, rax
0x18000c2d5  jz      short loc_18000C341
0x18000c2d7  cmp     qword ptr [rcx+50h], 0
0x18000c2dc  jnz     short loc_18000C341
0x18000c2de  test    rdx, rdx
0x18000c2e1  jz      short loc_18000C341
0x18000c2e3  mov     [rcx+38h], rdx
0x18000c2e7  mov     edi, 1
0x18000c2ec  mov     [rcx+40h], r8d
0x18000c2f0  mov     edx, edi; InfoLevel
0x18000c2f2  mov     [rcx+48h], r9
0x18000c2f6  lea     r8, [rsp+28h+Buffer]; Buffer
0x18000c2fb  mov     [rcx+50h], rax
0x18000c2ff  mov     rcx, r9; lpServer
0x18000c302  mov     [rsp+28h+Buffer], 0
0x18000c30b  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18000c311  mov     rcx, [rsp+28h+Buffer]; Buffer
0x18000c316  test    rcx, rcx
0x18000c319  jz      short loc_18000C330
0x18000c31b  test    dword ptr [rcx], 0FFFFFFFDh
0x18000c321  mov     edi, 0
0x18000c326  setz    dil
0x18000c32a  call    cs:__imp_DsRoleFreeMemory
0x18000c330  mov     eax, [rsp+28h+arg_28]
0x18000c334  mov     [rbx+134h], eax
0x18000c33a  xor     eax, eax
0x18000c33c  mov     [rbx+68h], edi
0x18000c33f  jmp     short loc_18000C346
0x18000c341  mov     eax, 80004003h
0x18000c346  mov     rbx, [rsp+28h+arg_0]
0x18000c34b  add     rsp, 20h
0x18000c34f  pop     rdi
0x18000c350  retn
```
