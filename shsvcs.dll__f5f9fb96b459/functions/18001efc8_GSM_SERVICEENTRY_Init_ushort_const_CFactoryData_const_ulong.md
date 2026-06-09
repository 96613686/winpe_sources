# GSM::SERVICEENTRY::Init(ushort const *,CFactoryData const *,ulong)

- ea: `0x18001efc8`
- end: `0x18001f147`
- name: `?Init@SERVICEENTRY@GSM@@QEAAJPEBGPEBVCFactoryData@@K@Z`
- size: `383`
- prototype: `__int64 __fastcall(GSM::SERVICEENTRY *this, const unsigned __int16 *, const struct CFactoryData *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074c0`

## callees

- `0x180017308`
- `0x180019148`
- `0x18001951c`
- `0x18001b404`
- `0x18001efc8`
- `0x1800237d4`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f07a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f0a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f07a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f0a5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001f014`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001f014`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f036`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f036`

## pseudocode

```c
__int64 __fastcall GSM::SERVICEENTRY::Init(
        GSM::SERVICEENTRY *this,
        const unsigned __int16 *a2,
        const struct CFactoryData *a3,
        int a4)
{
  HRESULT Error; // ebx
  int v9; // eax
  HANDLE EventW; // rax
  HANDLE v11; // rax
  _DWORD *v12; // rax
  GUID pguid; // [rsp+20h] [rbp-48h] BYREF

  *((_DWORD *)this + 4) = *((_DWORD *)this + 1);
  *((_DWORD *)this + 2) = 32;
  *((_DWORD *)this + 18) = 0;
  pguid = 0;
  Error = CoCreateGuid(&pguid);
  if ( Error < 0 )
    goto LABEL_14;
  v9 = StringFromGUID2(&pguid, (LPOLESTR)this + 38, 100);
  Error = v9 == 0 ? 0x8007007A : 0;
  if ( !v9 )
    goto LABEL_14;
  Error = StringCchCatW((unsigned __int16 *)this + 38, 0x64u, a2);
  if ( Error < 0 )
    goto LABEL_14;
  EventW = CreateEventW(0, 1, 0, (LPCWSTR)this + 38);
  *((_QWORD *)this + 35) = EventW;
  if ( !EventW )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_14;
  }
  v11 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 36) = v11;
  if ( !v11 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_14;
  }
  if ( (*(_BYTE *)this & 2) != 0 )
  {
    v12 = operator new(0x30u);
    if ( v12 )
    {
      v12[2] = 1;
      *(_QWORD *)v12 = &CCOMFactoryServer::`vftable';
      *((_QWORD *)v12 + 2) = a3;
      v12[6] = a4;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 5) = 0;
    }
    *((_QWORD *)this + 38) = v12;
    if ( !v12 )
    {
      Error = -2147024882;
LABEL_14:
      GSM::SERVICEENTRY::_Cleanup(this);
      return (unsigned int)Error;
    }
    Error = CCOMFactoryServer::Init((CCOMFactoryServer *)v12);
    if ( Error < 0 )
      goto LABEL_14;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001efc8  mov     [rsp+arg_10], rbx
0x18001efcd  push    rbp
0x18001efce  push    rsi
0x18001efcf  push    rdi
0x18001efd0  push    r14
0x18001efd2  push    r15
0x18001efd4  sub     rsp, 40h
0x18001efd8  mov     rax, cs:__security_cookie
0x18001efdf  xor     rax, rsp
0x18001efe2  mov     [rsp+68h+var_38], rax
0x18001efe7  mov     eax, [rcx+4]
0x18001efea  mov     rdi, rcx
0x18001efed  mov     [rcx+10h], eax
0x18001eff0  xorps   xmm0, xmm0
0x18001eff3  mov     dword ptr [rcx+8], 20h ; ' '
0x18001effa  mov     r14d, r9d
0x18001effd  mov     dword ptr [rcx+48h], 0
0x18001f004  mov     r15, r8
0x18001f007  lea     rcx, [rsp+68h+pguid]; pguid
0x18001f00c  mov     rbp, rdx
0x18001f00f  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x18001f014  call    cs:__imp_CoCreateGuid
0x18001f01a  mov     ebx, eax
0x18001f01c  test    eax, eax
0x18001f01e  js      loc_18001F11C
0x18001f024  lea     rsi, [rdi+4Ch]
0x18001f028  mov     r8d, 64h ; 'd'; cchMax
0x18001f02e  mov     rdx, rsi; lpsz
0x18001f031  lea     rcx, [rsp+68h+pguid]; rguid
0x18001f036  call    cs:__imp_StringFromGUID2
0x18001f03c  mov     ecx, eax
0x18001f03e  neg     ecx
0x18001f040  sbb     ebx, ebx
0x18001f042  not     ebx
0x18001f044  and     ebx, 8007007Ah
0x18001f04a  test    eax, eax
0x18001f04c  jz      loc_18001F11C
0x18001f052  mov     r8, rbp; unsigned __int16 *
0x18001f055  mov     edx, 64h ; 'd'; unsigned __int64
0x18001f05a  mov     rcx, rsi; unsigned __int16 *
0x18001f05d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f062  mov     ebx, eax
0x18001f064  test    eax, eax
0x18001f066  js      loc_18001F11C
0x18001f06c  xor     r8d, r8d; bInitialState
0x18001f06f  mov     r9, rsi; lpName
0x18001f072  xor     ecx, ecx; lpEventAttributes
0x18001f074  lea     esi, [r8+1]
0x18001f078  mov     edx, esi; bManualReset
0x18001f07a  call    cs:__imp_CreateEventW
0x18001f080  mov     [rdi+118h], rax
0x18001f087  test    rax, rax
0x18001f08a  jnz     short loc_18001F09B
0x18001f08c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f091  mov     ebx, eax
0x18001f093  test    eax, eax
0x18001f095  js      loc_18001F11C
0x18001f09b  xor     r9d, r9d; lpName
0x18001f09e  mov     r8d, esi; bInitialState
0x18001f0a1  mov     edx, esi; bManualReset
0x18001f0a3  xor     ecx, ecx; lpEventAttributes
0x18001f0a5  call    cs:__imp_CreateEventW
0x18001f0ab  mov     [rdi+120h], rax
0x18001f0b2  test    rax, rax
0x18001f0b5  jnz     short loc_18001F0C2
0x18001f0b7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f0bc  mov     ebx, eax
0x18001f0be  test    eax, eax
0x18001f0c0  js      short loc_18001F11C
0x18001f0c2  test    byte ptr [rdi], 2
0x18001f0c5  jz      short loc_18001F124
0x18001f0c7  mov     ecx, 30h ; '0'; Size
0x18001f0cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f0d1  test    rax, rax
0x18001f0d4  jz      short loc_18001F0FB
0x18001f0d6  lea     rcx, ??_7CCOMFactoryServer@@6B@; const CCOMFactoryServer::`vftable'
0x18001f0dd  mov     [rax+8], esi
0x18001f0e0  mov     [rax], rcx
0x18001f0e3  mov     [rax+10h], r15
0x18001f0e7  mov     [rax+18h], r14d
0x18001f0eb  mov     qword ptr [rax+20h], 0
0x18001f0f3  mov     qword ptr [rax+28h], 0
0x18001f0fb  mov     [rdi+130h], rax
0x18001f102  test    rax, rax
0x18001f105  jnz     short loc_18001F10E
0x18001f107  mov     ebx, 8007000Eh
0x18001f10c  jmp     short loc_18001F11C
0x18001f10e  mov     rcx, rax; this
0x18001f111  call    ?Init@CCOMFactoryServer@@QEAAJXZ; CCOMFactoryServer::Init(void)
0x18001f116  mov     ebx, eax
0x18001f118  test    eax, eax
0x18001f11a  jns     short loc_18001F124
0x18001f11c  mov     rcx, rdi; this
0x18001f11f  call    ?_Cleanup@SERVICEENTRY@GSM@@QEAAXXZ; GSM::SERVICEENTRY::_Cleanup(void)
0x18001f124  mov     eax, ebx
0x18001f126  mov     rcx, [rsp+68h+var_38]
0x18001f12b  xor     rcx, rsp; StackCookie
0x18001f12e  call    __security_check_cookie
0x18001f133  mov     rbx, [rsp+68h+arg_10]
0x18001f13b  add     rsp, 40h
0x18001f13f  pop     r15
0x18001f141  pop     r14
0x18001f143  pop     rdi
0x18001f144  pop     rsi
0x18001f145  pop     rbp
0x18001f146  retn
```
