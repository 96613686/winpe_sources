# CUserSetting::ReadError(long *,int)

- ea: `0x180005400`
- end: `0x18000547a`
- name: `?ReadError@CUserSetting@@IEAAJPEAJH@Z`
- size: `122`
- prototype: `int(CUserSetting *__hidden this, int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005d40`

## callees

- `0x180004eb0`
- `0x180005400`
- `0x18000892c`

## import_xrefs

- `WDSCORE!CurrentIP` at `0x180005438`
- `WDSCORE!CurrentIP` at `0x180005438`

## string_xrefs

- `0x180005456`: `CUserSetting::ReadError`

## pseudocode

```c
int __fastcall CUserSetting::ReadError(CUserSetting *this, int *a2, int a3)
{
  int result; // eax
  void *v5; // rax
  unsigned int v6; // ecx
  const unsigned __int16 *v7; // r9
  int v8; // ecx
  __int128 v9; // [rsp+30h] [rbp-18h] BYREF

  v9 = 0;
  result = CUserSetting::DeserializeField(this, L"Error", 4, (struct WDS_DATA *)&v9, a3);
  if ( result >= 0 )
  {
    v8 = DWORD2(v9);
  }
  else
  {
    if ( result == -2147352571 )
    {
      v5 = (void *)CurrentIP();
      Ui_Assert(v6, "hr != ((HRESULT)0x80020005L)", 0x19Cu, v7, L"CUserSetting::ReadError", v5);
    }
    v8 = 0;
    result = 0;
  }
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x180005400  push    rbx
0x180005402  sub     rsp, 40h
0x180005406  mov     rbx, rdx
0x180005409  mov     dword ptr [rsp+48h+var_28], r8d; int
0x18000540e  xorps   xmm0, xmm0
0x180005411  lea     rdx, aError; "Error"
0x180005418  mov     r8d, 4; unsigned int
0x18000541e  lea     r9, [rsp+48h+var_18]; struct WDS_DATA *
0x180005423  movups  [rsp+48h+var_18], xmm0
0x180005428  call    ?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z; CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)
0x18000542d  test    eax, eax
0x18000542f  jns     short loc_18000546D
0x180005431  cmp     eax, 80020005h
0x180005436  jnz     short loc_180005467
0x180005438  call    cs:__imp_CurrentIP
0x18000543f  nop     dword ptr [rax+rax+00h]
0x180005444  mov     [rsp+48h+var_20], rax; void *
0x180005449  mov     r8d, 19Ch; unsigned int
0x18000544f  lea     rdx, aHrHresult0x800; "hr != ((HRESULT)0x80020005L)"
0x180005456  lea     rax, aCusersettingRe_0; "CUserSetting::ReadError"
0x18000545d  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180005462  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180005467  xor     ecx, ecx
0x180005469  xor     eax, eax
0x18000546b  jmp     short loc_180005471
0x18000546d  mov     ecx, dword ptr [rsp+48h+var_18+8]
0x180005471  mov     [rbx], ecx
0x180005473  add     rsp, 40h
0x180005477  pop     rbx
0x180005478  retn
```
