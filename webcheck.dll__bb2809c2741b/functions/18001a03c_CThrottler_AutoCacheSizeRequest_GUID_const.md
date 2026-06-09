# CThrottler::AutoCacheSizeRequest(_GUID const *)

- ea: `0x18001a03c`
- end: `0x18001a171`
- name: `?AutoCacheSizeRequest@CThrottler@@AEAAJPEBU_GUID@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(CThrottler *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b090`

## callees

- `0x18001a03c`
- `0x18001a4b0`
- `0x18001a89c`
- `0x18001aaa0`

## import_xrefs

- `USER32!PostMessageW` at `0x18001a117`
- `USER32!PostMessageW` at `0x18001a117`
- `SHLWAPI!SHGetValueW` at `0x18001a08a`
- `SHLWAPI!SHGetValueW` at `0x18001a08a`

## string_xrefs

- `0x18001a05a`: `Cache`

## pseudocode

```c
__int64 __fastcall CThrottler::AutoCacheSizeRequest(HWND *this, const struct _GUID *a2)
{
  int v2; // esi
  unsigned int v5; // ebx
  int CookieIndexInQueue; // eax
  int v7; // eax
  __int64 v8; // rcx
  HWND v9; // rax
  DWORD pcbData[10]; // [rsp+30h] [rbp-28h] BYREF
  int pvData; // [rsp+70h] [rbp+18h] BYREF
  LPARAM lParam; // [rsp+78h] [rbp+20h] BYREF

  pcbData[0] = 4;
  v2 = 0;
  LODWORD(lParam) = 0;
  pvData = 0;
  v5 = -2147467259;
  if ( !SHGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Internet Explorer\\Control Panel",
          L"Cache",
          0,
          &pvData,
          pcbData)
    && pvData )
  {
    v2 = -2147467259;
  }
  CookieIndexInQueue = CThrottler::GetCookieIndexInQueue((CThrottler *)this, a2);
  if ( CookieIndexInQueue >= 0 )
  {
    _mm_lfence();
    if ( ((_DWORD)this[CookieIndexInQueue + 7][6] & 0x20000) == 0 )
      v2 = -2147467259;
    if ( v2 < 0 )
      return (unsigned int)v2;
    if ( ((_BYTE)this[13] & 0x20) == 0 )
    {
      if ( (int)CThrottler::IncreaseCacheSize((CThrottler *)this, (unsigned int *)&lParam) >= 0 )
        return 790416;
      if ( (int)++*((_DWORD *)this + 29) > 2 )
        return (unsigned int)-2147467260;
      if ( (int)CThrottler::CreateThrottlerWnd((CThrottler *)this) < 0 )
        return v5;
      PostMessageW(this[11], 0x465u, 0, (unsigned int)lParam);
      *((_DWORD *)this + 26) |= 0x20u;
    }
    v5 = -2147483638;
    v7 = CThrottler::GetCookieIndexInQueue((CThrottler *)this, a2);
    if ( v7 >= 0 )
    {
      _mm_lfence();
      v8 = v7;
      v9 = this[v7 + 7];
      *((_DWORD *)v9 + 6) &= ~4u;
      *((_DWORD *)this[v8 + 7] + 6) |= 2u;
      this[v8 + 7] = 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001a03c  mov     rax, rsp
0x18001a03f  mov     [rax+8], rbx
0x18001a043  push    rbp
0x18001a044  push    rsi
0x18001a045  push    rdi
0x18001a046  sub     rsp, 40h
0x18001a04a  mov     dword ptr [rax-28h], 4
0x18001a051  lea     rax, [rax-28h]
0x18001a055  mov     [rsp+58h+pcbData], rax; pcbData
0x18001a05a  lea     r8, aCache; "Cache"
0x18001a061  xor     esi, esi
0x18001a063  mov     rbp, rdx
0x18001a066  mov     [rax+48h], esi
0x18001a069  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Internet"...
0x18001a070  mov     [rax+40h], esi
0x18001a073  mov     rdi, rcx
0x18001a076  lea     rax, [rsp+58h+arg_10]
0x18001a07b  xor     r9d, r9d; pdwType
0x18001a07e  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001a085  mov     [rsp+58h+pvData], rax; pvData
0x18001a08a  call    cs:__imp_SHGetValueW
0x18001a090  mov     ebx, 80004005h
0x18001a095  test    eax, eax
0x18001a097  jnz     short loc_18001A0A0
0x18001a099  cmp     [rsp+58h+arg_10], esi
0x18001a09d  cmovnz  esi, ebx
0x18001a0a0  mov     rdx, rbp; struct _GUID *
0x18001a0a3  mov     rcx, rdi; this
0x18001a0a6  call    ?GetCookieIndexInQueue@CThrottler@@AEAAHPEBU_GUID@@@Z; CThrottler::GetCookieIndexInQueue(_GUID const *)
0x18001a0ab  test    eax, eax
0x18001a0ad  js      loc_18001A162
0x18001a0b3  lfence
0x18001a0b6  cdqe
0x18001a0b8  mov     rcx, [rdi+rax*8+38h]
0x18001a0bd  test    dword ptr [rcx+18h], 20000h
0x18001a0c4  jnz     short loc_18001A0C8
0x18001a0c6  mov     esi, ebx
0x18001a0c8  test    esi, esi
0x18001a0ca  js      short loc_18001A128
0x18001a0cc  test    byte ptr [rdi+68h], 20h
0x18001a0d0  jnz     short loc_18001A121
0x18001a0d2  lea     rdx, [rsp+58h+lParam]; unsigned int *
0x18001a0d7  mov     rcx, rdi; this
0x18001a0da  call    ?IncreaseCacheSize@CThrottler@@AEAAJPEAK@Z; CThrottler::IncreaseCacheSize(ulong *)
0x18001a0df  test    eax, eax
0x18001a0e1  js      short loc_18001A0EA
0x18001a0e3  mov     ebx, 0C0F90h
0x18001a0e8  jmp     short loc_18001A162
0x18001a0ea  inc     dword ptr [rdi+74h]
0x18001a0ed  cmp     dword ptr [rdi+74h], 2
0x18001a0f1  jle     short loc_18001A0FA
0x18001a0f3  mov     ebx, 80004004h
0x18001a0f8  jmp     short loc_18001A162
0x18001a0fa  mov     rcx, rdi; this
0x18001a0fd  call    ?CreateThrottlerWnd@CThrottler@@AEAAJXZ; CThrottler::CreateThrottlerWnd(void)
0x18001a102  test    eax, eax
0x18001a104  js      short loc_18001A162
0x18001a106  mov     r9d, dword ptr [rsp+58h+lParam]; lParam
0x18001a10b  xor     r8d, r8d; wParam
0x18001a10e  mov     rcx, [rdi+58h]; hWnd
0x18001a112  mov     edx, 465h; Msg
0x18001a117  call    cs:__imp_PostMessageW
0x18001a11d  or      dword ptr [rdi+68h], 20h
0x18001a121  mov     ebx, 8000000Ah
0x18001a126  jmp     short loc_18001A132
0x18001a128  mov     ebx, esi
0x18001a12a  cmp     esi, 8000000Ah
0x18001a130  jnz     short loc_18001A162
0x18001a132  mov     rdx, rbp; struct _GUID *
0x18001a135  mov     rcx, rdi; this
0x18001a138  call    ?GetCookieIndexInQueue@CThrottler@@AEAAHPEBU_GUID@@@Z; CThrottler::GetCookieIndexInQueue(_GUID const *)
0x18001a13d  test    eax, eax
0x18001a13f  js      short loc_18001A162
0x18001a141  lfence
0x18001a144  movsxd  rcx, eax
0x18001a147  mov     rax, [rdi+rcx*8+38h]
0x18001a14c  and     dword ptr [rax+18h], 0FFFFFFFBh
0x18001a150  mov     rax, [rdi+rcx*8+38h]
0x18001a155  or      dword ptr [rax+18h], 2
0x18001a159  mov     qword ptr [rdi+rcx*8+38h], 0
0x18001a162  mov     eax, ebx
0x18001a164  mov     rbx, [rsp+58h+arg_0]
0x18001a169  add     rsp, 40h
0x18001a16d  pop     rdi
0x18001a16e  pop     rsi
0x18001a16f  pop     rbp
0x18001a170  retn
```
