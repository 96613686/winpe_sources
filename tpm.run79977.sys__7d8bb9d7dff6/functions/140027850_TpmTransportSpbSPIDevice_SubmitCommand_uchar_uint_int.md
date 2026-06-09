# TpmTransportSpbSPIDevice::SubmitCommand(uchar *,uint,int)

- ea: `0x140027850`
- end: `0x140027a6f`
- name: `?SubmitCommand@TpmTransportSpbSPIDevice@@UEAAJPEAEIH@Z`
- size: `543`
- prototype: `__int64 __fastcall(TpmTransportSpbSPIDevice *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140026ac4`
- `0x140026cf8`
- `0x140026e08`
- `0x140026fd8`
- `0x140027128`
- `0x1400271d8`
- `0x140027850`
- `0x140039740`
- `0x140039840`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400278b1`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400278b1`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbSPIDevice::SubmitCommand(
        TpmTransportSpbSPIDevice *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4)
{
  int v5; // r12d
  __int64 result; // rax
  __int64 v10; // rbx
  union _LARGE_INTEGER v11; // rbx
  unsigned int v12; // ecx
  unsigned int v13; // edi
  unsigned __int8 v14[4]; // [rsp+30h] [rbp-A9h] BYREF
  unsigned __int16 v15; // [rsp+34h] [rbp-A5h] BYREF
  unsigned __int8 v16[4]; // [rsp+38h] [rbp-A1h] BYREF
  char v17; // [rsp+3Ch] [rbp-9Dh]
  unsigned __int8 v18[4]; // [rsp+40h] [rbp-99h] BYREF
  char v19; // [rsp+44h] [rbp-95h]
  unsigned __int8 v20[80]; // [rsp+50h] [rbp-89h] BYREF
  unsigned __int8 v21[80]; // [rsp+A0h] [rbp-39h] BYREF

  v5 = 0;
  v14[0] = 0;
  v15 = 0;
  result = TpmTransportSpbSPIDevice::SPITISRequestLocality(this, (__int64)a2, a4);
  if ( (int)result >= 0 )
  {
    v10 = MEMORY[0xFFFFF78000000320];
    v11.QuadPart = 0x989680uLL / KeQueryTimeIncrement() + v10;
    result = TpmTransportSpbSPIDevice::SPITISGetStatus(this, v14, v11, a4);
    if ( (int)result >= 0 )
    {
      if ( (v14[0] & 0x40) != 0 || (result = TpmTransportSpbSPIDevice::SPITISWaitForAbort(this, a4), (int)result >= 0) )
      {
        memset(v20, 0, 0x44u);
        memset(v21, 0, 0x44u);
        *(_WORD *)&v20[1] = 212;
        v20[3] = 36;
        while ( 1 )
        {
          result = TpmTransportSpbSPIDevice::SPITISGetBurstCount(this, &v15, v11, a4);
          if ( (int)result < 0 )
            break;
          if ( !v15 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
            }
            return 3221225862LL;
          }
          v12 = v15;
          if ( v15 >= 0x40u )
            v12 = 64;
          if ( a3 >= v12 )
          {
            v13 = v15;
            if ( v15 >= 0x40u )
              v13 = 64;
          }
          else
          {
            v13 = a3;
          }
          v20[0] = (v13 - 1) & 0x3F;
          memmove(&v20[4], &a2[v5], v13);
          result = TpmTransportSpbSPIDevice::SPIFullDuplexSync(this, v20, v21, v13 + 4, v11, a4);
          if ( (int)result < 0 )
            return result;
          a3 -= v13;
          if ( !a3 )
          {
            result = TpmTransportSpbSPIDevice::SPITISWaitForStatus(this, 0x80u, v11, a4);
            if ( (int)result >= 0 )
            {
              *(_DWORD *)v16 = 402707456;
              *(_DWORD *)v18 = 0;
              v19 = 0;
              v17 = 32;
              return TpmTransportSpbSPIDevice::SPIFullDuplexSync(this, v16, v18, 5u, v11, a4);
            }
            return result;
          }
          v5 += v13;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027850  mov     [rsp-8+arg_18], rbx
0x140027855  push    rbp
0x140027856  push    rsi
0x140027857  push    rdi
0x140027858  push    r12
0x14002785a  push    r13
0x14002785c  push    r14
0x14002785e  push    r15
0x140027860  lea     rbp, [rsp-27h]
0x140027865  sub     rsp, 100h
0x14002786c  mov     rax, cs:__security_cookie
0x140027873  xor     rax, rsp
0x140027876  mov     [rbp+57h+var_40], rax
0x14002787a  mov     r15d, r8d
0x14002787d  xor     r12d, r12d
0x140027880  mov     r8d, r9d; int
0x140027883  mov     [rsp+130h+var_100], r12b
0x140027888  mov     [rsp+130h+var_FC], r12w
0x14002788e  mov     esi, r9d
0x140027891  mov     r13, rdx
0x140027894  mov     r14, rcx
0x140027897  call    ?SPITISRequestLocality@TpmTransportSpbSPIDevice@@IEAAJ_JH@Z; TpmTransportSpbSPIDevice::SPITISRequestLocality(__int64,int)
0x14002789c  test    eax, eax
0x14002789e  js      loc_140027A47
0x1400278a4  mov     rdi, 0FFFFF78000000320h
0x1400278ae  mov     rbx, [rdi]
0x1400278b1  call    cs:__imp_KeQueryTimeIncrement
0x1400278b8  nop     dword ptr [rax+rax+00h]
0x1400278bd  mov     ecx, eax
0x1400278bf  xor     edx, edx
0x1400278c1  mov     eax, 989680h
0x1400278c6  mov     r9d, esi; int
0x1400278c9  div     rcx
0x1400278cc  lea     rdx, [rsp+130h+var_100]; unsigned __int8 *
0x1400278d1  mov     rcx, r14; this
0x1400278d4  add     rbx, rax
0x1400278d7  mov     r8, rbx; union _LARGE_INTEGER
0x1400278da  call    ?SPITISGetStatus@TpmTransportSpbSPIDevice@@IEAAJPEAET_LARGE_INTEGER@@H@Z; TpmTransportSpbSPIDevice::SPITISGetStatus(uchar *,_LARGE_INTEGER,int)
0x1400278df  test    eax, eax
0x1400278e1  js      loc_140027A47
0x1400278e7  test    [rsp+130h+var_100], 40h
0x1400278ec  jnz     short loc_140027900
0x1400278ee  mov     edx, esi; int
0x1400278f0  mov     rcx, r14; this
0x1400278f3  call    ?SPITISWaitForAbort@TpmTransportSpbSPIDevice@@IEAAJH@Z; TpmTransportSpbSPIDevice::SPITISWaitForAbort(int)
0x1400278f8  test    eax, eax
0x1400278fa  js      loc_140027A47
0x140027900  mov     edi, 44h ; 'D'
0x140027905  lea     rcx, [rsp+130h+var_E0]; void *
0x14002790a  mov     r8d, edi; Size
0x14002790d  xor     edx, edx; Val
0x14002790f  call    memset
0x140027914  mov     r8d, edi; Size
0x140027917  lea     rcx, [rbp+57h+var_90]; void *
0x14002791b  xor     edx, edx; Val
0x14002791d  call    memset
0x140027922  mov     [rsp+130h+var_DF], 0D4h
0x140027929  mov     [rsp+130h+var_DD], 24h ; '$'
0x14002792e  mov     r9d, esi; int
0x140027931  lea     rdx, [rsp+130h+var_FC]; unsigned __int16 *
0x140027936  mov     r8, rbx; union _LARGE_INTEGER
0x140027939  mov     rcx, r14; this
0x14002793c  call    ?SPITISGetBurstCount@TpmTransportSpbSPIDevice@@IEAAJPEAGT_LARGE_INTEGER@@H@Z; TpmTransportSpbSPIDevice::SPITISGetBurstCount(ushort *,_LARGE_INTEGER,int)
0x140027941  test    eax, eax
0x140027943  js      loc_140027A47
0x140027949  movzx   eax, [rsp+130h+var_FC]
0x14002794e  test    ax, ax
0x140027951  jz      loc_140027A13
0x140027957  mov     edx, 40h ; '@'
0x14002795c  mov     ecx, eax
0x14002795e  cmp     ax, dx
0x140027961  jb      short loc_140027965
0x140027963  mov     ecx, edx
0x140027965  cmp     r15d, ecx
0x140027968  jnb     short loc_14002796F
0x14002796a  mov     edi, r15d
0x14002796d  jmp     short loc_140027978
0x14002796f  mov     edi, eax
0x140027971  cmp     ax, dx
0x140027974  jb      short loc_140027978
0x140027976  mov     edi, edx
0x140027978  lea     eax, [rdi-1]
0x14002797b  mov     edx, r12d
0x14002797e  and     al, 3Fh
0x140027980  mov     r8d, edi; Size
0x140027983  add     rdx, r13; Src
0x140027986  mov     [rsp+130h+var_E0], al
0x14002798a  lea     rcx, [rsp+130h+var_DC]; void *
0x14002798f  call    memmove
0x140027994  lea     r9d, [rdi+4]; unsigned int
0x140027998  mov     [rsp+130h+var_108], esi; int
0x14002799c  lea     r8, [rbp+57h+var_90]; unsigned __int8 *
0x1400279a0  mov     qword ptr [rsp+130h+var_110], rbx; union _LARGE_INTEGER
0x1400279a5  lea     rdx, [rsp+130h+var_E0]; unsigned __int8 *
0x1400279aa  mov     rcx, r14; this
0x1400279ad  call    ?SPIFullDuplexSync@TpmTransportSpbSPIDevice@@IEAAJPEAE0IT_LARGE_INTEGER@@H@Z; TpmTransportSpbSPIDevice::SPIFullDuplexSync(uchar *,uchar *,uint,_LARGE_INTEGER,int)
0x1400279b2  test    eax, eax
0x1400279b4  js      loc_140027A47
0x1400279ba  sub     r15d, edi
0x1400279bd  jz      short loc_1400279C7
0x1400279bf  add     r12d, edi
0x1400279c2  jmp     loc_14002792E
0x1400279c7  mov     r9d, esi; int
0x1400279ca  mov     r8, rbx; union _LARGE_INTEGER
0x1400279cd  mov     dl, 80h; unsigned __int8
0x1400279cf  mov     rcx, r14; this
0x1400279d2  call    ?SPITISWaitForStatus@TpmTransportSpbSPIDevice@@IEAAJET_LARGE_INTEGER@@H@Z; TpmTransportSpbSPIDevice::SPITISWaitForStatus(uchar,_LARGE_INTEGER,int)
0x1400279d7  test    eax, eax
0x1400279d9  js      short loc_140027A47
0x1400279db  xor     eax, eax
0x1400279dd  mov     dword ptr [rsp+130h+var_F8], 1800D400h
0x1400279e5  mov     dword ptr [rsp+130h+var_F0], eax
0x1400279e9  mov     [rsp+130h+var_EC], al
0x1400279ed  mov     [rsp+130h+var_F4], 20h ; ' '
0x1400279f2  mov     [rsp+130h+var_108], esi; int
0x1400279f6  lea     r9d, [rax+5]; unsigned int
0x1400279fa  lea     r8, [rsp+130h+var_F0]; unsigned __int8 *
0x1400279ff  mov     qword ptr [rsp+130h+var_110], rbx; union _LARGE_INTEGER
0x140027a04  lea     rdx, [rsp+130h+var_F8]; unsigned __int8 *
0x140027a09  mov     rcx, r14; this
0x140027a0c  call    ?SPIFullDuplexSync@TpmTransportSpbSPIDevice@@IEAAJPEAE0IT_LARGE_INTEGER@@H@Z; TpmTransportSpbSPIDevice::SPIFullDuplexSync(uchar *,uchar *,uint,_LARGE_INTEGER,int)
0x140027a11  jmp     short loc_140027A47
0x140027a13  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027a1a  lea     rax, WPP_GLOBAL_Control
0x140027a21  cmp     rcx, rax
0x140027a24  jz      short loc_140027A42
0x140027a26  mov     eax, [rcx+2Ch]
0x140027a29  test    al, 4
0x140027a2b  jz      short loc_140027A42
0x140027a2d  mov     rcx, [rcx+18h]
0x140027a31  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x140027a38  mov     edx, 0Ah
0x140027a3d  call    WPP_SF_
0x140027a42  mov     eax, 0C0000186h
0x140027a47  mov     rcx, [rbp+57h+var_40]
0x140027a4b  xor     rcx, rsp; StackCookie
0x140027a4e  call    __security_check_cookie
0x140027a53  mov     rbx, [rsp+130h+arg_18]
0x140027a5b  add     rsp, 100h
0x140027a62  pop     r15
0x140027a64  pop     r14
0x140027a66  pop     r13
0x140027a68  pop     r12
0x140027a6a  pop     rdi
0x140027a6b  pop     rsi
0x140027a6c  pop     rbp
0x140027a6d  retn
```
