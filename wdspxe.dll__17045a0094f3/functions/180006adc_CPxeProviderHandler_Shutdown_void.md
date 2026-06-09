# CPxeProviderHandler::Shutdown(void)

- ea: `0x180006adc`
- end: `0x180006d26`
- name: `?Shutdown@CPxeProviderHandler@@QEAAKXZ`
- size: `586`
- prototype: `unsigned int __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003150`
- `0x180004b84`
- `0x18000523c`

## callees

- `0x180004004`
- `0x180004848`
- `0x180006adc`
- `0x1800070c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006be6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006ca9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cc3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cd7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006be6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006ca9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cc3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cd7`
- `KERNEL32!EnterCriticalSection` at `0x180006afd`
- `KERNEL32!EnterCriticalSection` at `0x180006b0d`
- `KERNEL32!EnterCriticalSection` at `0x180006bff`
- `KERNEL32!EnterCriticalSection` at `0x180006afd`
- `KERNEL32!EnterCriticalSection` at `0x180006b0d`
- `KERNEL32!EnterCriticalSection` at `0x180006bff`
- `KERNEL32!LeaveCriticalSection` at `0x180006b21`
- `KERNEL32!LeaveCriticalSection` at `0x180006c13`
- `KERNEL32!LeaveCriticalSection` at `0x180006cef`
- `KERNEL32!LeaveCriticalSection` at `0x180006b21`
- `KERNEL32!LeaveCriticalSection` at `0x180006c13`
- `KERNEL32!LeaveCriticalSection` at `0x180006cef`
- `WdsCommonLib!?Shutdown@CBannedDeviceIds@@QEAAKXZ` at `0x180006d02`
- `WdsCommonLib!?Shutdown@CBannedDeviceIds@@QEAAKXZ` at `0x180006d02`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::Shutdown(CPxeProviderHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 v3; // rdi
  CPxeProvider *v4; // rbx
  CPxeProvider *v5; // rax
  CPxeProvider *v6; // rdi
  CPxeProvider *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rbx
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = *((_QWORD *)this + 1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v3 )
  {
    v4 = (CPxeProvider *)*((_QWORD *)this + 1);
    while ( 1 )
    {
      if ( !v4 )
        goto LABEL_14;
      v5 = (CPxeProvider *)*((_QWORD *)this + 1);
      v6 = v4;
      v7 = (CPxeProvider *)*((_QWORD *)this + 2);
      if ( v5 == v7 )
        break;
      if ( v4 != v5 )
      {
        if ( v4 != v7 )
        {
          v10 = (_QWORD *)((char *)v4 + 152);
          v4 = (CPxeProvider *)*((_QWORD *)v4 + 19);
          *(_QWORD *)(*((_QWORD *)v6 + 20) + 152LL) = v4;
          *(_QWORD *)(*v10 + 160LL) = *((_QWORD *)v6 + 20);
          goto LABEL_11;
        }
        v9 = *((_QWORD *)v7 + 20);
        *((_QWORD *)this + 2) = v9;
        *(_QWORD *)(v9 + 152) = 0;
        goto LABEL_9;
      }
      v8 = *((_QWORD *)v5 + 19);
      *((_QWORD *)this + 1) = v8;
      *(_QWORD *)(v8 + 160) = 0;
      v4 = (CPxeProvider *)*((_QWORD *)this + 1);
LABEL_11:
      --*((_DWORD *)this + 16);
      v11 = CPxeProvider::Shutdown(v6);
      ElValidateWin32_2(v11, v12, v13, 0x2D5u);
      CPxeProvider::~CPxeProvider(v6);
      operator delete(v6);
    }
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 1) = 0;
LABEL_9:
    v4 = 0;
    goto LABEL_11;
  }
LABEL_14:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v14 = *((_QWORD *)this + 9);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v14 )
  {
    v15 = (_QWORD *)*((_QWORD *)this + 9);
    while ( 1 )
    {
      if ( !v15 )
        goto LABEL_31;
      v16 = (_QWORD *)*((_QWORD *)this + 9);
      v17 = v15;
      v18 = (_QWORD *)*((_QWORD *)this + 10);
      if ( v16 == v18 )
        break;
      if ( v15 != v16 )
      {
        if ( v15 != v18 )
        {
          v21 = v15 + 4;
          v15 = (_QWORD *)v15[4];
          *(_QWORD *)(v17[5] + 32LL) = v15;
          *(_QWORD *)(*v21 + 40LL) = v17[5];
          goto LABEL_24;
        }
        v20 = v18[5];
        *((_QWORD *)this + 10) = v20;
        *(_QWORD *)(v20 + 32) = 0;
        goto LABEL_22;
      }
      v19 = v16[4];
      *((_QWORD *)this + 9) = v19;
      *(_QWORD *)(v19 + 40) = 0;
      v15 = (_QWORD *)*((_QWORD *)this + 9);
LABEL_24:
      --*((_DWORD *)this + 32);
      v22 = (void *)v17[1];
      if ( v22 )
      {
        operator delete(v22);
        v17[1] = 0;
      }
      v23 = (void *)v17[2];
      if ( v23 )
      {
        operator delete(v23);
        v17[2] = 0;
      }
      operator delete(v17);
    }
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 9) = 0;
LABEL_22:
    v15 = 0;
    goto LABEL_24;
  }
LABEL_31:
  LeaveCriticalSection(v1);
  CBannedDeviceIds::Shutdown((CPxeProviderHandler *)((char *)this + 136));
  return 0;
}

```

## disassembly

```asm
0x180006adc  mov     [rsp+arg_0], rbx
0x180006ae1  mov     [rsp+arg_8], rbp
0x180006ae6  mov     [rsp+arg_10], rsi
0x180006aeb  push    rdi
0x180006aec  sub     rsp, 20h
0x180006af0  lea     rbp, [rcx+150h]
0x180006af7  mov     rsi, rcx
0x180006afa  mov     rcx, rbp; lpCriticalSection
0x180006afd  call    cs:__imp_EnterCriticalSection
0x180006b04  nop     dword ptr [rax+rax+00h]
0x180006b09  lea     rcx, [rsi+18h]; lpCriticalSection
0x180006b0d  call    cs:__imp_EnterCriticalSection
0x180006b14  nop     dword ptr [rax+rax+00h]
0x180006b19  mov     rdi, [rsi+8]
0x180006b1d  lea     rcx, [rsi+18h]; lpCriticalSection
0x180006b21  call    cs:__imp_LeaveCriticalSection
0x180006b28  nop     dword ptr [rax+rax+00h]
0x180006b2d  test    rdi, rdi
0x180006b30  jz      loc_180006BFB
0x180006b36  mov     rbx, [rsi+8]
0x180006b3a  jmp     loc_180006BF2
0x180006b3f  mov     rax, [rsi+8]
0x180006b43  mov     rdi, rbx
0x180006b46  mov     rcx, [rsi+10h]
0x180006b4a  cmp     rax, rcx
0x180006b4d  jnz     short loc_180006B5B
0x180006b4f  and     qword ptr [rsi+10h], 0
0x180006b54  and     qword ptr [rsi+8], 0
0x180006b59  jmp     short loc_180006B91
0x180006b5b  cmp     rbx, rax
0x180006b5e  jnz     short loc_180006B79
0x180006b60  mov     rax, [rax+98h]
0x180006b67  mov     [rsi+8], rax
0x180006b6b  and     qword ptr [rax+0A0h], 0
0x180006b73  mov     rbx, [rsi+8]
0x180006b77  jmp     short loc_180006BBE
0x180006b79  cmp     rbx, rcx
0x180006b7c  jnz     short loc_180006B95
0x180006b7e  mov     rax, [rcx+0A0h]
0x180006b85  mov     [rsi+10h], rax
0x180006b89  and     qword ptr [rax+98h], 0
0x180006b91  xor     ebx, ebx
0x180006b93  jmp     short loc_180006BBE
0x180006b95  mov     rax, [rdi+0A0h]
0x180006b9c  lea     rcx, [rbx+98h]
0x180006ba3  mov     rbx, [rcx]
0x180006ba6  mov     [rax+98h], rbx
0x180006bad  mov     rcx, [rcx]
0x180006bb0  mov     rax, [rdi+0A0h]
0x180006bb7  mov     [rcx+0A0h], rax
0x180006bbe  dec     dword ptr [rsi+40h]
0x180006bc1  mov     rcx, rdi; this
0x180006bc4  call    ?Shutdown@CPxeProvider@@QEAAKXZ; CPxeProvider::Shutdown(void)
0x180006bc9  mov     ecx, eax
0x180006bcb  mov     r9d, 2D5h
0x180006bd1  call    ElValidateWin32_2
0x180006bd6  test    rdi, rdi
0x180006bd9  jz      short loc_180006BF2
0x180006bdb  mov     rcx, rdi; this
0x180006bde  call    ??1CPxeProvider@@QEAA@XZ; CPxeProvider::~CPxeProvider(void)
0x180006be3  mov     rcx, rdi
0x180006be6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006bed  nop     dword ptr [rax+rax+00h]
0x180006bf2  test    rbx, rbx
0x180006bf5  jnz     loc_180006B3F
0x180006bfb  lea     rcx, [rsi+58h]; lpCriticalSection
0x180006bff  call    cs:__imp_EnterCriticalSection
0x180006c06  nop     dword ptr [rax+rax+00h]
0x180006c0b  mov     rbx, [rsi+48h]
0x180006c0f  lea     rcx, [rsi+58h]; lpCriticalSection
0x180006c13  call    cs:__imp_LeaveCriticalSection
0x180006c1a  nop     dword ptr [rax+rax+00h]
0x180006c1f  test    rbx, rbx
0x180006c22  jz      loc_180006CEC
0x180006c28  mov     rbx, [rsi+48h]
0x180006c2c  jmp     loc_180006CE3
0x180006c31  mov     rax, [rsi+48h]
0x180006c35  mov     rdi, rbx
0x180006c38  mov     rcx, [rsi+50h]
0x180006c3c  cmp     rax, rcx
0x180006c3f  jnz     short loc_180006C4D
0x180006c41  and     qword ptr [rsi+50h], 0
0x180006c46  and     qword ptr [rsi+48h], 0
0x180006c4b  jmp     short loc_180006C77
0x180006c4d  cmp     rbx, rax
0x180006c50  jnz     short loc_180006C65
0x180006c52  mov     rax, [rax+20h]
0x180006c56  mov     [rsi+48h], rax
0x180006c5a  and     qword ptr [rax+28h], 0
0x180006c5f  mov     rbx, [rsi+48h]
0x180006c63  jmp     short loc_180006C95
0x180006c65  cmp     rbx, rcx
0x180006c68  jnz     short loc_180006C7B
0x180006c6a  mov     rax, [rcx+28h]
0x180006c6e  mov     [rsi+50h], rax
0x180006c72  and     qword ptr [rax+20h], 0
0x180006c77  xor     ebx, ebx
0x180006c79  jmp     short loc_180006C95
0x180006c7b  mov     rax, [rdi+28h]
0x180006c7f  lea     rcx, [rbx+20h]
0x180006c83  mov     rbx, [rcx]
0x180006c86  mov     [rax+20h], rbx
0x180006c8a  mov     rcx, [rcx]
0x180006c8d  mov     rax, [rdi+28h]
0x180006c91  mov     [rcx+28h], rax
0x180006c95  dec     dword ptr [rsi+80h]
0x180006c9b  test    rdi, rdi
0x180006c9e  jz      short loc_180006CE3
0x180006ca0  mov     rcx, [rdi+8]
0x180006ca4  test    rcx, rcx
0x180006ca7  jz      short loc_180006CBA
0x180006ca9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006cb0  nop     dword ptr [rax+rax+00h]
0x180006cb5  and     qword ptr [rdi+8], 0
0x180006cba  mov     rcx, [rdi+10h]
0x180006cbe  test    rcx, rcx
0x180006cc1  jz      short loc_180006CD4
0x180006cc3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006cca  nop     dword ptr [rax+rax+00h]
0x180006ccf  and     qword ptr [rdi+10h], 0
0x180006cd4  mov     rcx, rdi
0x180006cd7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006cde  nop     dword ptr [rax+rax+00h]
0x180006ce3  test    rbx, rbx
0x180006ce6  jnz     loc_180006C31
0x180006cec  mov     rcx, rbp; lpCriticalSection
0x180006cef  call    cs:__imp_LeaveCriticalSection
0x180006cf6  nop     dword ptr [rax+rax+00h]
0x180006cfb  lea     rcx, [rsi+88h]
0x180006d02  call    cs:__imp_?Shutdown@CBannedDeviceIds@@QEAAKXZ; CBannedDeviceIds::Shutdown(void)
0x180006d09  nop     dword ptr [rax+rax+00h]
0x180006d0e  mov     rbx, [rsp+28h+arg_0]
0x180006d13  xor     eax, eax
0x180006d15  mov     rbp, [rsp+28h+arg_8]
0x180006d1a  mov     rsi, [rsp+28h+arg_10]
0x180006d1f  add     rsp, 20h
0x180006d23  pop     rdi
0x180006d24  retn
```
