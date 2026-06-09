# CSessionKey::GetHandles(ATL::CCryptKey &,ATL::CCryptHMACHash &)

- ea: `0x180010188`
- end: `0x180010274`
- name: `?GetHandles@CSessionKey@@AEAAJAEAVCCryptKey@ATL@@AEAVCCryptHMACHash@3@@Z`
- size: `236`
- prototype: `int(CSessionKey *__hidden this, struct ATL::CCryptKey *, struct ATL::CCryptHMACHash *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fbc0`
- `0x18000fda0`

## callees

- `0x18000fa9c`
- `0x18000fac0`
- `0x180010188`
- `0x18001040c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c4`
- `CRYPTSP!CryptSetHashParam` at `0x18001024f`
- `CRYPTSP!CryptSetHashParam` at `0x18001024f`
- `CRYPTSP!CryptCreateHash` at `0x180010212`
- `CRYPTSP!CryptCreateHash` at `0x180010212`

## pseudocode

```c
int __fastcall CSessionKey::GetHandles(CSessionKey *this, HCRYPTKEY *a2, HCRYPTHASH *a3)
{
  int result; // eax
  unsigned int v7; // r9d
  HCRYPTHASH v8; // rcx
  int v9; // eax
  BYTE pbData[16]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp-18h]
  int v13; // [rsp+70h] [rbp+8h] BYREF

  if ( !*(_DWORD *)this )
    return -2147188621;
  ATL::CCryptKey::Attach(a2, *((_QWORD *)this + 2), 0);
  if ( *a2 )
  {
    v13 = 1;
    result = ATL::CCryptKey::SetParam((ATL::CCryptKey *)a2, 4u, (unsigned __int8 *)&v13, v7);
    if ( result >= 0 )
    {
      if ( CryptCreateHash(*((_QWORD *)this + 1), 0x8009u, *((_QWORD *)this + 3), 0, a3)
        || (result = ATL::AtlHresultFromLastError(), result >= 0) )
      {
        v8 = *a3;
        v12 = 0;
        v9 = *((_DWORD *)this + 9);
        *(_OWORD *)pbData = 0;
        *(_DWORD *)pbData = v9;
        v11 = 0;
        if ( CryptSetHashParam(v8, 5u, pbData, 0) )
          return 0;
        else
          return ATL::AtlHresultFromLastError();
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180010188  mov     [rsp+arg_8], rbx
0x18001018d  mov     [rsp+arg_10], rsi
0x180010192  push    rdi
0x180010193  sub     rsp, 60h
0x180010197  cmp     dword ptr [rcx], 0
0x18001019a  mov     rsi, r8
0x18001019d  mov     rdi, rdx
0x1800101a0  mov     rbx, rcx
0x1800101a3  jnz     short loc_1800101AF
0x1800101a5  mov     eax, 80048073h
0x1800101aa  jmp     loc_180010262
0x1800101af  mov     rdx, [rcx+10h]; hKey
0x1800101b3  xor     r8d, r8d; int
0x1800101b6  mov     rcx, rdi; phKey
0x1800101b9  call    ?Attach@CCryptKey@ATL@@QEAAX_KH@Z; ATL::CCryptKey::Attach(unsigned __int64,int)
0x1800101be  cmp     qword ptr [rdi], 0
0x1800101c2  jnz     short loc_1800101DF
0x1800101c4  call    cs:__imp_GetLastError
0x1800101ca  test    eax, eax
0x1800101cc  jle     loc_180010262
0x1800101d2  movzx   eax, ax
0x1800101d5  or      eax, 80070000h
0x1800101da  jmp     loc_180010262
0x1800101df  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x1800101e4  mov     [rsp+68h+arg_0], 1
0x1800101ec  mov     edx, 4; unsigned int
0x1800101f1  mov     rcx, rdi; this
0x1800101f4  call    ?SetParam@CCryptKey@ATL@@QEAAJKPEAEK@Z; ATL::CCryptKey::SetParam(ulong,uchar *,ulong)
0x1800101f9  test    eax, eax
0x1800101fb  js      short loc_180010262
0x1800101fd  mov     r8, [rbx+18h]; hKey
0x180010201  xor     r9d, r9d; dwFlags
0x180010204  mov     rcx, [rbx+8]; hProv
0x180010208  mov     edx, 8009h; Algid
0x18001020d  mov     [rsp+68h+phHash], rsi; phHash
0x180010212  call    cs:__imp_CryptCreateHash
0x180010218  test    eax, eax
0x18001021a  jnz     short loc_180010225
0x18001021c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010221  test    eax, eax
0x180010223  js      short loc_180010262
0x180010225  mov     rcx, [rsi]; hHash
0x180010228  lea     r8, [rsp+68h+pbData]; pbData
0x18001022d  xor     eax, eax
0x18001022f  xorps   xmm0, xmm0
0x180010232  xor     r9d, r9d; dwFlags
0x180010235  mov     [rsp+68h+var_18], rax
0x18001023a  mov     eax, [rbx+24h]
0x18001023d  movups  xmmword ptr [rsp+68h+pbData], xmm0
0x180010242  mov     dword ptr [rsp+68h+pbData], eax
0x180010246  lea     edx, [r9+5]; dwParam
0x18001024a  movups  [rsp+68h+var_28], xmm0
0x18001024f  call    cs:__imp_CryptSetHashParam
0x180010255  test    eax, eax
0x180010257  jnz     short loc_180010260
0x180010259  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001025e  jmp     short loc_180010262
0x180010260  xor     eax, eax
0x180010262  lea     r11, [rsp+68h+var_8]
0x180010267  mov     rbx, [r11+18h]
0x18001026b  mov     rsi, [r11+20h]
0x18001026f  mov     rsp, r11
0x180010272  pop     rdi
0x180010273  retn
```
