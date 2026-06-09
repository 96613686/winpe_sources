# CWsmTrackingConfig::CTrackingConfig::SetLogSessionInfo(ushort const *,ushort const *)

- ea: `0x14000bcdc`
- end: `0x14000bde7`
- name: `?SetLogSessionInfo@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBG0@Z`
- size: `267`
- prototype: `__int64 __fastcall(CWsmTrackingConfig::CTrackingConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000bdf0`

## callees

- `0x14000bcdc`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bdab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bdbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bdab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bdbf`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::SetLogSessionInfo(
        CWsmTrackingConfig::CTrackingConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v5; // rcx
  __int64 result; // rax
  unsigned int v7; // ebx
  void **v8; // rsi
  void *v9; // rcx
  __int64 *v10; // rax
  __int64 v11; // rcx
  void **v12; // rsi
  void *v13; // rcx
  _QWORD *v14; // rax

  v5 = (_QWORD *)((char *)this + 56);
  if ( a2 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
    v7 = result;
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    v8 = (void **)v5[1];
    v7 = 0;
    v5[1] = 0;
    if ( v8 )
    {
      v9 = *v8;
      if ( *v8 != v8 + 2 && v9 )
        ExFreePoolWithTag(v9, 0x6E6D7377u);
      ExFreePoolWithTag(v8, 0x6E6D7377u);
    }
  }
  v10 = (__int64 *)*((_QWORD *)this + 8);
  if ( v10 )
    v11 = *v10;
  else
    v11 = 0;
  *((_QWORD *)this + 11) = v11;
  if ( a3 )
  {
    result = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 9) + 16LL))(
               (char *)this + 72,
               a3);
    v7 = result;
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    v12 = (void **)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    if ( v12 )
    {
      v13 = *v12;
      if ( *v12 != v12 + 2 && v13 )
        ExFreePoolWithTag(v13, 0x6E6D7377u);
      ExFreePoolWithTag(v12, 0x6E6D7377u);
    }
  }
  v14 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v14 )
    v14 = (_QWORD *)*v14;
  *((_QWORD *)this + 12) = v14;
  return v7;
}

```

## disassembly

```asm
0x14000bcdc  push    rbx
0x14000bcde  push    rbp
0x14000bcdf  push    rsi
0x14000bce0  push    rdi
0x14000bce1  sub     rsp, 28h
0x14000bce5  mov     rdi, rcx
0x14000bce8  mov     rbp, r8
0x14000bceb  add     rcx, 38h ; '8'
0x14000bcef  test    rdx, rdx
0x14000bcf2  jz      short loc_14000BD0B
0x14000bcf4  mov     rax, [rcx]
0x14000bcf7  mov     rax, [rax+10h]
0x14000bcfb  call    _guard_dispatch_icall
0x14000bd00  mov     ebx, eax
0x14000bd02  test    eax, eax
0x14000bd04  jns     short loc_14000BD50
0x14000bd06  jmp     loc_14000BDDD
0x14000bd0b  mov     rsi, [rcx+8]
0x14000bd0f  xor     ebx, ebx
0x14000bd11  mov     [rcx+8], rbx
0x14000bd15  test    rsi, rsi
0x14000bd18  jz      short loc_14000BD50
0x14000bd1a  mov     rcx, [rsi]; P
0x14000bd1d  lea     rax, [rsi+10h]
0x14000bd21  cmp     rcx, rax
0x14000bd24  jz      short loc_14000BD3C
0x14000bd26  test    rcx, rcx
0x14000bd29  jz      short loc_14000BD3C
0x14000bd2b  mov     edx, 6E6D7377h; Tag
0x14000bd30  call    cs:__imp_ExFreePoolWithTag
0x14000bd37  nop     dword ptr [rax+rax+00h]
0x14000bd3c  mov     edx, 6E6D7377h; Tag
0x14000bd41  mov     rcx, rsi; P
0x14000bd44  call    cs:__imp_ExFreePoolWithTag
0x14000bd4b  nop     dword ptr [rax+rax+00h]
0x14000bd50  mov     rax, [rdi+40h]
0x14000bd54  test    rax, rax
0x14000bd57  jz      short loc_14000BD5E
0x14000bd59  mov     rcx, [rax]
0x14000bd5c  jmp     short loc_14000BD60
0x14000bd5e  xor     ecx, ecx
0x14000bd60  mov     [rdi+58h], rcx
0x14000bd64  lea     rcx, [rdi+48h]
0x14000bd68  test    rbp, rbp
0x14000bd6b  jz      short loc_14000BD84
0x14000bd6d  mov     rax, [rcx]
0x14000bd70  mov     rdx, rbp
0x14000bd73  mov     rax, [rax+10h]
0x14000bd77  call    _guard_dispatch_icall
0x14000bd7c  mov     ebx, eax
0x14000bd7e  test    eax, eax
0x14000bd80  jns     short loc_14000BDCB
0x14000bd82  jmp     short loc_14000BDDD
0x14000bd84  mov     rsi, [rcx+8]
0x14000bd88  mov     qword ptr [rcx+8], 0
0x14000bd90  test    rsi, rsi
0x14000bd93  jz      short loc_14000BDCB
0x14000bd95  mov     rcx, [rsi]; P
0x14000bd98  lea     rax, [rsi+10h]
0x14000bd9c  cmp     rcx, rax
0x14000bd9f  jz      short loc_14000BDB7
0x14000bda1  test    rcx, rcx
0x14000bda4  jz      short loc_14000BDB7
0x14000bda6  mov     edx, 6E6D7377h; Tag
0x14000bdab  call    cs:__imp_ExFreePoolWithTag
0x14000bdb2  nop     dword ptr [rax+rax+00h]
0x14000bdb7  mov     edx, 6E6D7377h; Tag
0x14000bdbc  mov     rcx, rsi; P
0x14000bdbf  call    cs:__imp_ExFreePoolWithTag
0x14000bdc6  nop     dword ptr [rax+rax+00h]
0x14000bdcb  mov     rax, [rdi+50h]
0x14000bdcf  test    rax, rax
0x14000bdd2  jz      short loc_14000BDD7
0x14000bdd4  mov     rax, [rax]
0x14000bdd7  mov     [rdi+60h], rax
0x14000bddb  mov     eax, ebx
0x14000bddd  add     rsp, 28h
0x14000bde1  pop     rdi
0x14000bde2  pop     rsi
0x14000bde3  pop     rbp
0x14000bde4  pop     rbx
0x14000bde5  retn
```
