# TpmTransportSpbI2CDevice::SubmitCommand(uchar *,uint,int)

- ea: `0x140027400`
- end: `0x1400275c4`
- name: `?SubmitCommand@TpmTransportSpbI2CDevice@@UEAAJPEAEIH@Z`
- size: `452`
- prototype: `__int64 __fastcall(TpmTransportSpbI2CDevice *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140025880`
- `0x140025938`
- `0x140025a54`
- `0x140025b64`
- `0x140025c20`
- `0x140027400`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140027448`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140027494`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140027448`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140027494`

## pseudocode

```c
int __fastcall TpmTransportSpbI2CDevice::SubmitCommand(
        TpmTransportSpbI2CDevice *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4)
{
  int result; // eax
  __int64 v9; // rbx
  union _LARGE_INTEGER v10; // rbx
  bool v11; // r9
  unsigned int v12; // edi
  __int64 v13; // rdi
  union _LARGE_INTEGER v14; // rdi
  union _LARGE_INTEGER v15; // r8
  int v16; // esi
  unsigned int v17; // ecx
  unsigned __int8 v18[4]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 v19[42]; // [rsp+34h] [rbp-54h] BYREF
  unsigned __int8 v20; // [rsp+A0h] [rbp+18h] BYREF

  v20 = 0;
  v19[0] = 0;
  result = TpmTransportSpbI2CDevice::I2CTISRequestLocality(this, (__int64)a2, a4);
  if ( result >= 0 )
  {
    v9 = MEMORY[0xFFFFF78000000320];
    v10.QuadPart = 0x989680uLL / KeQueryTimeIncrement() + v9;
    result = TpmTransportSpbI2CDevice::I2CTISGetStatus(this, &v20, v10, v11);
    if ( result >= 0 )
    {
      v12 = 64;
      if ( (v20 & 0x40) != 0
        || (v18[0] = 64,
            v13 = MEMORY[0xFFFFF78000000320],
            v14.QuadPart = 0x989680uLL / KeQueryTimeIncrement() + v13,
            result = TpmTransportSpbI2CDevice::I2CWriteRegister(this, 24, v18, 1u),
            result >= 0)
        && (v15 = v14,
            v12 = 64,
            result = TpmTransportSpbI2CDevice::I2CTISWaitForStatus(this, 0x40u, v15, a4),
            result >= 0) )
      {
        v16 = 0;
        while ( 1 )
        {
          result = TpmTransportSpbI2CDevice::I2CTISGetBurstCount(this, v19, v10, a4);
          if ( result < 0 )
            break;
          if ( !v19[0] )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
            }
            return -1073741434;
          }
          v17 = v19[0];
          if ( v19[0] >= 0x40u )
            v17 = 64;
          if ( a3 >= v17 )
          {
            if ( v19[0] < 0x40u )
              v12 = v19[0];
          }
          else
          {
            v12 = a3;
          }
          result = TpmTransportSpbI2CDevice::I2CWriteRegister(this, 36, &a2[v16], v12);
          if ( result < 0 )
            return result;
          a3 -= v12;
          if ( !a3 )
          {
            result = TpmTransportSpbI2CDevice::I2CTISWaitForStatus(this, 0x80u, v10, a4);
            if ( result >= 0 )
            {
              v18[0] = 32;
              return TpmTransportSpbI2CDevice::I2CWriteRegister(this, 24, v18, 1u);
            }
            return result;
          }
          v16 += v12;
          v12 = 64;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027400  mov     rax, rsp
0x140027403  push    rbx
0x140027404  push    rbp
0x140027405  push    rsi
0x140027406  push    rdi
0x140027407  push    r12
0x140027409  push    r13
0x14002740b  push    r14
0x14002740d  push    r15
0x14002740f  sub     rsp, 48h
0x140027413  mov     r14d, r8d
0x140027416  xor     r13d, r13d
0x140027419  mov     r8d, r9d; int
0x14002741c  mov     [rax+18h], r13b
0x140027420  mov     [rax-54h], r13w
0x140027425  mov     r15d, r9d
0x140027428  mov     r12, rdx
0x14002742b  mov     rbp, rcx
0x14002742e  call    ?I2CTISRequestLocality@TpmTransportSpbI2CDevice@@IEAAJ_JH@Z; TpmTransportSpbI2CDevice::I2CTISRequestLocality(__int64,int)
0x140027433  test    eax, eax
0x140027435  js      loc_1400275B2
0x14002743b  mov     rsi, 0FFFFF78000000320h
0x140027445  mov     rbx, [rsi]
0x140027448  call    cs:__imp_KeQueryTimeIncrement
0x14002744f  nop     dword ptr [rax+rax+00h]
0x140027454  mov     ecx, eax
0x140027456  xor     edx, edx
0x140027458  mov     eax, 989680h
0x14002745d  div     rcx
0x140027460  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x140027468  mov     rcx, rbp; this
0x14002746b  add     rbx, rax
0x14002746e  mov     r8, rbx; union _LARGE_INTEGER
0x140027471  call    ?I2CTISGetStatus@TpmTransportSpbI2CDevice@@IEAAJPEAET_LARGE_INTEGER@@_N@Z; TpmTransportSpbI2CDevice::I2CTISGetStatus(uchar *,_LARGE_INTEGER,bool)
0x140027476  test    eax, eax
0x140027478  js      loc_1400275B2
0x14002747e  lea     edi, [r13+40h]
0x140027482  test    [rsp+88h+arg_10], dil
0x14002748a  jnz     short loc_1400274E7
0x14002748c  mov     [rsp+88h+var_58], dil
0x140027491  mov     rdi, [rsi]
0x140027494  call    cs:__imp_KeQueryTimeIncrement
0x14002749b  nop     dword ptr [rax+rax+00h]
0x1400274a0  mov     ecx, eax
0x1400274a2  xor     edx, edx
0x1400274a4  mov     eax, 989680h
0x1400274a9  lea     r9d, [r13+1]; unsigned int
0x1400274ad  div     rcx
0x1400274b0  lea     r8, [rsp+88h+var_58]; unsigned __int8 *
0x1400274b5  mov     dl, 18h; unsigned __int8
0x1400274b7  mov     rcx, rbp; this
0x1400274ba  add     rdi, rax
0x1400274bd  call    ?I2CWriteRegister@TpmTransportSpbI2CDevice@@IEAAJEPEBEIT_LARGE_INTEGER@@_N@Z; TpmTransportSpbI2CDevice::I2CWriteRegister(uchar,uchar const *,uint,_LARGE_INTEGER,bool)
0x1400274c2  test    eax, eax
0x1400274c4  js      loc_1400275B2
0x1400274ca  mov     r8, rdi; union _LARGE_INTEGER
0x1400274cd  mov     r9d, r15d; int
0x1400274d0  lea     edi, [r13+40h]
0x1400274d4  mov     rcx, rbp; this
0x1400274d7  mov     dl, dil; unsigned __int8
0x1400274da  call    ?I2CTISWaitForStatus@TpmTransportSpbI2CDevice@@IEAAJET_LARGE_INTEGER@@H@Z; TpmTransportSpbI2CDevice::I2CTISWaitForStatus(uchar,_LARGE_INTEGER,int)
0x1400274df  test    eax, eax
0x1400274e1  js      loc_1400275B2
0x1400274e7  mov     esi, r13d
0x1400274ea  mov     r9d, r15d; int
0x1400274ed  lea     rdx, [rsp+88h+var_54]; unsigned __int16 *
0x1400274f2  mov     r8, rbx; union _LARGE_INTEGER
0x1400274f5  mov     rcx, rbp; this
0x1400274f8  call    ?I2CTISGetBurstCount@TpmTransportSpbI2CDevice@@IEAAJPEAGT_LARGE_INTEGER@@H@Z; TpmTransportSpbI2CDevice::I2CTISGetBurstCount(ushort *,_LARGE_INTEGER,int)
0x1400274fd  test    eax, eax
0x1400274ff  js      loc_1400275B2
0x140027505  movzx   eax, [rsp+88h+var_54]
0x14002750a  test    ax, ax
0x14002750d  jz      short loc_14002757E
0x14002750f  mov     ecx, eax
0x140027511  cmp     ax, di
0x140027514  jb      short loc_140027518
0x140027516  mov     ecx, edi
0x140027518  cmp     r14d, ecx
0x14002751b  jnb     short loc_140027522
0x14002751d  mov     edi, r14d
0x140027520  jmp     short loc_140027529
0x140027522  cmp     ax, di
0x140027525  jnb     short loc_140027529
0x140027527  mov     edi, eax
0x140027529  mov     r8d, esi
0x14002752c  mov     r9d, edi; unsigned int
0x14002752f  add     r8, r12; unsigned __int8 *
0x140027532  mov     dl, 24h ; '$'; unsigned __int8
0x140027534  mov     rcx, rbp; this
0x140027537  call    ?I2CWriteRegister@TpmTransportSpbI2CDevice@@IEAAJEPEBEIT_LARGE_INTEGER@@_N@Z; TpmTransportSpbI2CDevice::I2CWriteRegister(uchar,uchar const *,uint,_LARGE_INTEGER,bool)
0x14002753c  test    eax, eax
0x14002753e  js      short loc_1400275B2
0x140027540  sub     r14d, edi
0x140027543  jz      short loc_14002754E
0x140027545  add     esi, edi
0x140027547  mov     edi, 40h ; '@'
0x14002754c  jmp     short loc_1400274EA
0x14002754e  mov     r9d, r15d; int
0x140027551  mov     r8, rbx; union _LARGE_INTEGER
0x140027554  mov     dl, 80h; unsigned __int8
0x140027556  mov     rcx, rbp; this
0x140027559  call    ?I2CTISWaitForStatus@TpmTransportSpbI2CDevice@@IEAAJET_LARGE_INTEGER@@H@Z; TpmTransportSpbI2CDevice::I2CTISWaitForStatus(uchar,_LARGE_INTEGER,int)
0x14002755e  test    eax, eax
0x140027560  js      short loc_1400275B2
0x140027562  mov     [rsp+88h+var_58], 20h ; ' '
0x140027567  mov     r9d, 1; unsigned int
0x14002756d  lea     r8, [rsp+88h+var_58]; unsigned __int8 *
0x140027572  mov     dl, 18h; unsigned __int8
0x140027574  mov     rcx, rbp; this
0x140027577  call    ?I2CWriteRegister@TpmTransportSpbI2CDevice@@IEAAJEPEBEIT_LARGE_INTEGER@@_N@Z; TpmTransportSpbI2CDevice::I2CWriteRegister(uchar,uchar const *,uint,_LARGE_INTEGER,bool)
0x14002757c  jmp     short loc_1400275B2
0x14002757e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027585  lea     rax, WPP_GLOBAL_Control
0x14002758c  cmp     rcx, rax
0x14002758f  jz      short loc_1400275AD
0x140027591  mov     eax, [rcx+2Ch]
0x140027594  test    al, 4
0x140027596  jz      short loc_1400275AD
0x140027598  mov     rcx, [rcx+18h]
0x14002759c  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x1400275a3  mov     edx, 13h
0x1400275a8  call    WPP_SF_
0x1400275ad  mov     eax, 0C0000186h
0x1400275b2  add     rsp, 48h
0x1400275b6  pop     r15
0x1400275b8  pop     r14
0x1400275ba  pop     r13
0x1400275bc  pop     r12
0x1400275be  pop     rdi
0x1400275bf  pop     rsi
0x1400275c0  pop     rbp
0x1400275c1  pop     rbx
0x1400275c2  retn
```
