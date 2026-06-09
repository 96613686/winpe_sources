# FormatSRB

- ea: `0x180045b68`
- end: `0x180045feb`
- name: `FormatSRB`
- size: `1155`
- prototype: `__int64 __fastcall(void *Src, STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180043390`

## callees

- `0x1800113a8`
- `0x1800207c0`
- `0x180021490`
- `0x180023b05`
- `0x180045b68`
- `0x180046ecc`

## string_xrefs

- `0x180045eca`: `Data path`
- `0x180045c8d`: `SRB extension`
- `0x180045f05`: `SRB extension`

## pseudocode

```c
__int64 __fastcall FormatSRB(unsigned __int16 *Src, STRSAFE_LPWSTR pszDest, int a3)
{
  unsigned __int64 v3; // rbx
  unsigned int v6; // ecx
  __int64 result; // rax
  wchar_t *v8; // r10
  unsigned int v9; // edi
  unsigned int i; // ebx
  __int64 v11; // [rsp+30h] [rbp-170h]
  __int64 v12; // [rsp+38h] [rbp-168h]
  STRSAFE_LPWSTR pszDesta; // [rsp+120h] [rbp-80h] BYREF
  unsigned __int64 v14; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v15[2]; // [rsp+130h] [rbp-70h] BYREF
  unsigned __int8 v16; // [rsp+132h] [rbp-6Eh]
  unsigned __int8 v17; // [rsp+133h] [rbp-6Dh]
  unsigned __int8 v18; // [rsp+134h] [rbp-6Ch]
  unsigned __int8 v19; // [rsp+135h] [rbp-6Bh]
  unsigned __int8 v20; // [rsp+136h] [rbp-6Ah]
  unsigned __int8 v21; // [rsp+137h] [rbp-69h]
  unsigned __int8 v22; // [rsp+138h] [rbp-68h]
  unsigned __int8 v23; // [rsp+139h] [rbp-67h]
  unsigned __int8 v24; // [rsp+13Ah] [rbp-66h]
  unsigned __int8 v25; // [rsp+13Bh] [rbp-65h]
  int v26; // [rsp+13Ch] [rbp-64h]
  int v27; // [rsp+140h] [rbp-60h]
  int v28; // [rsp+144h] [rbp-5Ch]
  __int64 v29; // [rsp+148h] [rbp-58h]
  __int64 v30; // [rsp+150h] [rbp-50h]
  __int64 v31; // [rsp+160h] [rbp-40h]
  __int64 v32; // [rsp+168h] [rbp-38h]
  int v33; // [rsp+170h] [rbp-30h]
  _BYTE v34[24]; // [rsp+178h] [rbp-28h]
  _BYTE v35[12]; // [rsp+190h] [rbp-10h] BYREF
  int v36; // [rsp+19Ch] [rbp-4h]
  int v37; // [rsp+1A0h] [rbp+0h]
  int v38; // [rsp+1A4h] [rbp+4h]
  __int64 v39; // [rsp+1A8h] [rbp+8h]
  __int64 v40; // [rsp+1B0h] [rbp+10h]
  __int64 v41; // [rsp+1C0h] [rbp+20h]
  __int64 v42; // [rsp+1C8h] [rbp+28h]

  v3 = a3;
  memset_0(v15, 0, 0x58u);
  memset_0(v35, 0, 0x58u);
  v6 = *Src;
  result = 0;
  pszDesta = pszDest;
  v14 = v3;
  pszDest[v3 - 1] = 0;
  if ( (unsigned __int16)v6 <= 0x58u )
  {
    if ( *((_BYTE *)Src + 2) == 23 )
    {
      memcpy_0(v35, Src, v6);
      return StringCchPrintfW(
               pszDest,
               v3,
               L"\n"
                "%30hs: %s\n"
                "%30hs: 0x%02X\n"
                "%30hs: 0x%02X\n"
                "%30hs: 0x%02x,0x%02x,0x%02x\n"
                "%30hs: 0x%02X\n"
                "%30hs: 0x%08X\n"
                "%30hs: 0x%08X\n"
                "%30hs: 0x%p\n"
                "%30hs: 0x%p\n"
                "%30hs: 0x%p\n"
                "%30hs: Length 0x%08XBuffer 0x%p\n",
               "Function",
               off_1800505B0[v35[2]],
               "Sub function",
               v35[4],
               "SRB status",
               v35[3],
               "Device address",
               v35[5],
               v35[6],
               v35[7],
               "WMI flags",
               v35[9],
               "SRB flags",
               v36,
               "Timeout value",
               v38,
               "Original request",
               v41,
               "SRB extension",
               v42,
               "Data path",
               v40,
               "Data",
               v37,
               v39);
    }
    else
    {
      memcpy_0(v15, Src, v6);
      StringCchPrintfExW(
        pszDest,
        v3,
        &pszDesta,
        &v14,
        0,
        L"\n"
         "%30hs: %s\n"
         "%30hs: 0x%02X\n"
         "%30hs: 0x%02X\n"
         "%30hs: 0x%02x,0x%02x,0x%02x\n"
         "%30hs: 0x%02X\n"
         "%30hs: 0x%02X\n"
         "%30hs: 0x%08X\n"
         "%30hs: 0x%08X\n"
         "%30hs: 0x%p\n"
         "%30hs: 0x%p\n"
         "%30hs: 0x%08X\n"
         "%30hs: Length 0x%08X Buffer 0x%p\n"
         "%30hs: Length 0x%08X Buffer 0x%p",
        "Function",
        off_1800505B0[v16],
        "SRB status",
        v17,
        "SCSI status",
        v18,
        "Device address",
        v19,
        v20,
        v21,
        "Queue tag",
        v22,
        "Queue Action",
        v23,
        "SRB flags",
        v26,
        "Timeout value",
        v28,
        "Original request",
        v31,
        "SRB extension",
        v32,
        "Internal status/Sort key",
        v33,
        "Sense info",
        v25,
        v30,
        "Data",
        v27,
        v29);
      v8 = pszDesta;
      if ( !v16 )
      {
        v9 = v24;
        LODWORD(v12) = v24;
        StringCchPrintfExW(pszDesta, v14, &pszDesta, &v14, 0, L"\n%30hs: Length 0x%02X", "CDB", v12);
        v8 = pszDesta;
        for ( i = 0; i < v9; ++i )
        {
          if ( i == 15 * (i / 0xF) )
          {
            StringCchPrintfExW(v8, v14, &pszDesta, &v14, 0, L"\n%30hs ", " ");
            v8 = pszDesta;
          }
          LODWORD(v11) = (unsigned __int8)v34[i];
          StringCchPrintfExW(v8, v14, &pszDesta, &v14, 0, L"%02X ", v11);
          v8 = pszDesta;
        }
      }
      return StringCchPrintfExW(v8, v14, &pszDesta, &v14, 0, L"\n");
    }
  }
  return result;
}

```

## disassembly

```asm
0x180045b68  push    rbp
0x180045b6a  push    rbx
0x180045b6b  push    rsi
0x180045b6c  push    rdi
0x180045b6d  push    r12
0x180045b6f  push    r13
0x180045b71  push    r15
0x180045b73  lea     rbp, [rsp-60h]
0x180045b78  sub     rsp, 200h
0x180045b7f  mov     rax, cs:__security_cookie
0x180045b86  xor     rax, rsp
0x180045b89  mov     [rbp+90h+var_40], rax
0x180045b8d  movsxd  rbx, r8d
0x180045b90  mov     r15, rdx
0x180045b93  mov     rdi, rcx
0x180045b96  mov     esi, 58h ; 'X'
0x180045b9b  mov     r8d, esi; Size
0x180045b9e  lea     rcx, [rbp+90h+var_100]; void *
0x180045ba2  xor     edx, edx; Val
0x180045ba4  call    memset_0
0x180045ba9  mov     r8d, esi; Size
0x180045bac  lea     rcx, [rbp+90h+var_A0]; void *
0x180045bb0  xor     edx, edx; Val
0x180045bb2  call    memset_0
0x180045bb7  movzx   ecx, word ptr [rdi]
0x180045bba  xor     eax, eax
0x180045bbc  mov     [rbp+90h+pszDest], r15
0x180045bc0  mov     r12, rbx
0x180045bc3  mov     [rbp+90h+var_108], rbx
0x180045bc7  mov     [r15+rbx*2-2], ax
0x180045bcd  cmp     cx, si
0x180045bd0  ja      loc_180045FCD
0x180045bd6  cmp     byte ptr [rdi+2], 17h
0x180045bda  mov     r8d, ecx; Size
0x180045bdd  mov     rdx, rdi; Src
0x180045be0  jz      loc_180045E89
0x180045be6  lea     rcx, [rbp+90h+var_100]; void *
0x180045bea  call    memcpy_0
0x180045bef  mov     rax, [rbp+90h+var_E8]
0x180045bf3  lea     r13, off_1800505B0; "SRB_FUNCTION_EXECUTE_SCSI"
0x180045bfa  mov     [rsp+230h+var_118], rax
0x180045c02  mov     eax, [rbp+90h+var_F0]
0x180045c05  mov     [rsp+230h+var_120], eax
0x180045c0c  lea     rax, aData; "Data"
0x180045c13  mov     [rsp+230h+var_128], rax
0x180045c1b  mov     rax, [rbp+90h+var_E0]
0x180045c1f  mov     [rsp+230h+var_130], rax
0x180045c27  lea     rax, aSenseInfo; "Sense info"
0x180045c2e  movzx   ecx, [rbp+90h+var_F5]
0x180045c32  movzx   edx, [rbp+90h+var_F7]
0x180045c36  movzx   r8d, [rbp+90h+var_F8]
0x180045c3b  movzx   r9d, [rbp+90h+var_F9]
0x180045c40  movzx   r10d, [rbp+90h+var_FA]
0x180045c45  movzx   r11d, [rbp+90h+var_FB]
0x180045c4a  movzx   esi, [rbp+90h+var_FE]
0x180045c4e  movzx   ebx, [rbp+90h+var_FC]
0x180045c52  movzx   edi, [rbp+90h+var_FD]
0x180045c56  mov     [rsp+230h+var_138], ecx
0x180045c5d  mov     rcx, r15; pszDest
0x180045c60  mov     [rsp+230h+var_140], rax
0x180045c68  mov     eax, [rbp+90h+var_C0]
0x180045c6b  mov     [rsp+230h+var_148], eax
0x180045c72  lea     rax, aInternalStatus; "Internal status/Sort key"
0x180045c79  mov     [rsp+230h+var_150], rax
0x180045c81  mov     rax, [rbp+90h+var_C8]
0x180045c85  mov     [rsp+230h+var_158], rax
0x180045c8d  lea     rax, aSrbExtension; "SRB extension"
0x180045c94  mov     [rsp+230h+var_160], rax
0x180045c9c  mov     rax, [rbp+90h+var_D0]
0x180045ca0  mov     [rsp+230h+var_168], rax
0x180045ca8  lea     rax, aOriginalReques; "Original request"
0x180045caf  mov     [rsp+230h+var_170], rax
0x180045cb7  mov     eax, [rbp+90h+var_EC]
0x180045cba  mov     dword ptr [rsp+230h+var_178], eax
0x180045cc1  lea     rax, aTimeoutValue; "Timeout value"
0x180045cc8  mov     [rsp+230h+var_180], rax
0x180045cd0  mov     eax, [rbp+90h+var_F4]
0x180045cd3  mov     dword ptr [rsp+230h+var_188], eax
0x180045cda  lea     rax, aSrbFlags; "SRB flags"
0x180045ce1  mov     [rsp+230h+var_190], rax
0x180045ce9  lea     rax, aQueueAction; "Queue Action"
0x180045cf0  mov     dword ptr [rsp+230h+var_198], edx
0x180045cf7  mov     rdx, r12; unsigned __int64
0x180045cfa  mov     [rsp+230h+var_1A0], rax
0x180045d02  lea     rax, aQueueTag; "Queue tag"
0x180045d09  mov     dword ptr [rsp+230h+var_1A8], r8d
0x180045d11  lea     r8, [rbp+90h+pszDest]; unsigned __int16 **
0x180045d15  mov     [rsp+230h+var_1B0], rax
0x180045d1d  lea     rax, aDeviceAddress; "Device address"
0x180045d24  mov     dword ptr [rsp+230h+var_1B8], r9d
0x180045d29  lea     r9, aFunction; "Function"
0x180045d30  mov     [rsp+230h+var_1C0], r10d
0x180045d35  mov     dword ptr [rsp+230h+var_1C8], r11d
0x180045d3a  mov     [rsp+230h+var_1D0], rax
0x180045d3f  lea     rax, aScsiStatus; "SCSI status"
0x180045d46  mov     [rsp+230h+var_1D8], ebx
0x180045d4a  mov     [rsp+230h+var_1E0], rax
0x180045d4f  lea     rax, aSrbStatus; "SRB status"
0x180045d56  mov     dword ptr [rsp+230h+var_1E8], edi
0x180045d5a  mov     [rsp+230h+var_1F0], rax
0x180045d5f  mov     rax, [r13+rsi*8+0]
0x180045d64  xor     esi, esi
0x180045d66  mov     [rsp+230h+var_1F8], rax
0x180045d6b  lea     rax, a30hsS30hs0x02x_0; "\n%30hs: %s\n%30hs: 0x%02X\n%30hs: 0x%0"...
0x180045d72  mov     [rsp+230h+var_200], r9
0x180045d77  lea     r9, [rbp+90h+var_108]; unsigned __int64 *
0x180045d7b  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x180045d80  mov     qword ptr [rsp+230h+var_210], rsi; unsigned int
0x180045d85  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045d8a  mov     r10, [rbp+90h+pszDest]
0x180045d8e  cmp     [rbp+90h+var_FE], sil
0x180045d92  jnz     loc_180045E5F
0x180045d98  movzx   edi, [rbp+90h+var_F6]
0x180045d9c  lea     rax, aCdb; "CDB"
0x180045da3  mov     rdx, [rbp+90h+var_108]; unsigned __int64
0x180045da7  lea     r9, [rbp+90h+var_108]; unsigned __int64 *
0x180045dab  mov     dword ptr [rsp+230h+var_1F8], edi
0x180045daf  lea     r8, [rbp+90h+pszDest]; unsigned __int16 **
0x180045db3  mov     [rsp+230h+var_200], rax
0x180045db8  mov     rcx, r10; pszDest
0x180045dbb  lea     rax, a30hsLength0x02; "\n%30hs: Length 0x%02X"
0x180045dc2  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x180045dc7  mov     qword ptr [rsp+230h+var_210], rsi; unsigned int
0x180045dcc  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045dd1  mov     r10, [rbp+90h+pszDest]
0x180045dd5  mov     ebx, esi
0x180045dd7  test    edi, edi
0x180045dd9  jz      loc_180045E5F
0x180045ddf  mov     eax, 88888889h
0x180045de4  mul     ebx
0x180045de6  shr     edx, 3
0x180045de9  imul    ecx, edx, 0Fh
0x180045dec  cmp     ebx, ecx
0x180045dee  jnz     short loc_180045E25
0x180045df0  mov     rdx, [rbp+90h+var_108]; unsigned __int64
0x180045df4  lea     rax, asc_18006099C; " "
0x180045dfb  mov     [rsp+230h+var_200], rax
0x180045e00  lea     r9, [rbp+90h+var_108]; unsigned __int64 *
0x180045e04  lea     rax, a30hs; "\n%30hs "
0x180045e0b  mov     rcx, r10; pszDest
0x180045e0e  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x180045e13  lea     r8, [rbp+90h+pszDest]; unsigned __int16 **
0x180045e17  mov     qword ptr [rsp+230h+var_210], rsi; unsigned int
0x180045e1c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045e21  mov     r10, [rbp+90h+pszDest]
0x180045e25  mov     rdx, [rbp+90h+var_108]; unsigned __int64
0x180045e29  lea     r9, [rbp+90h+var_108]; unsigned __int64 *
0x180045e2d  mov     eax, ebx
0x180045e2f  lea     r8, [rbp+90h+pszDest]; unsigned __int16 **
0x180045e33  movzx   ecx, [rbp+rax+90h+var_B8]
0x180045e38  lea     rax, a02x_1; "%02X "
0x180045e3f  mov     dword ptr [rsp+230h+var_200], ecx
0x180045e43  mov     rcx, r10; pszDest
0x180045e46  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x180045e4b  mov     qword ptr [rsp+230h+var_210], rsi; unsigned int
0x180045e50  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045e55  mov     r10, [rbp+90h+pszDest]
0x180045e59  inc     ebx
0x180045e5b  cmp     ebx, edi
0x180045e5d  jb      short loc_180045DDF
0x180045e5f  mov     rdx, [rbp+90h+var_108]; unsigned __int64
0x180045e63  lea     rax, asc_18005C7F0; "\n"
0x180045e6a  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x180045e6f  lea     r9, [rbp+90h+var_108]; unsigned __int64 *
0x180045e73  lea     r8, [rbp+90h+pszDest]; unsigned __int16 **
0x180045e77  mov     qword ptr [rsp+230h+var_210], rsi; unsigned int
0x180045e7c  mov     rcx, r10; pszDest
0x180045e7f  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045e84  jmp     loc_180045FCD
0x180045e89  lea     rcx, [rbp+90h+var_A0]; void *
0x180045e8d  call    memcpy_0
0x180045e92  mov     rax, [rbp+90h+var_88]
0x180045e96  lea     r13, off_1800505B0; "SRB_FUNCTION_EXECUTE_SCSI"
0x180045e9d  mov     [rsp+230h+var_158], rax
0x180045ea5  mov     eax, [rbp+90h+var_90]
0x180045ea8  mov     dword ptr [rsp+230h+var_160], eax
0x180045eaf  lea     rax, aData; "Data"
0x180045eb6  mov     [rsp+230h+var_168], rax
0x180045ebe  mov     rax, [rbp+90h+var_80]
0x180045ec2  mov     [rsp+230h+var_170], rax
0x180045eca  lea     rax, aDataPath; "Data path"
0x180045ed1  movzx   ecx, [rbp+90h+var_97]
0x180045ed5  movzx   edx, [rbp+90h+var_99]
0x180045ed9  movzx   r8d, [rbp+90h+var_9A]
0x180045ede  movzx   r9d, [rbp+90h+var_9B]
0x180045ee3  movzx   r10d, [rbp+90h+var_9D]
0x180045ee8  mov     [rsp+230h+var_178], rax
0x180045ef0  mov     rax, [rbp+90h+var_68]
0x180045ef4  movzx   r11d, [rbp+90h+var_9C]
0x180045ef9  movzx   ebx, [rbp+90h+var_9E]
0x180045efd  mov     [rsp+230h+var_180], rax
0x180045f05  lea     rax, aSrbExtension; "SRB extension"
0x180045f0c  mov     [rsp+230h+var_188], rax
0x180045f14  mov     rax, [rbp+90h+var_70]
0x180045f18  mov     [rsp+230h+var_190], rax
0x180045f20  lea     rax, aOriginalReques; "Original request"
0x180045f27  mov     [rsp+230h+var_198], rax
0x180045f2f  mov     eax, [rbp+90h+var_8C]
0x180045f32  mov     dword ptr [rsp+230h+var_1A0], eax
0x180045f39  lea     rax, aTimeoutValue; "Timeout value"
0x180045f40  mov     [rsp+230h+var_1A8], rax
0x180045f48  mov     eax, [rbp+90h+var_94]
0x180045f4b  mov     dword ptr [rsp+230h+var_1B0], eax
0x180045f52  lea     rax, aSrbFlags; "SRB flags"
0x180045f59  mov     [rsp+230h+var_1B8], rax
0x180045f5e  lea     rax, aWmiFlags; "WMI flags"
0x180045f65  mov     [rsp+230h+var_1C0], ecx
0x180045f69  mov     rcx, r15; unsigned __int16 *
0x180045f6c  mov     [rsp+230h+var_1C8], rax
0x180045f71  lea     rax, aDeviceAddress; "Device address"
0x180045f78  mov     dword ptr [rsp+230h+var_1D0], edx
0x180045f7c  mov     rdx, r12; unsigned __int64
0x180045f7f  mov     [rsp+230h+var_1D8], r8d
0x180045f84  lea     r8, a30hsS30hs0x02x; "\n%30hs: %s\n%30hs: 0x%02X\n%30hs: 0x%0"...
0x180045f8b  mov     dword ptr [rsp+230h+var_1E0], r9d
0x180045f90  lea     r9, aFunction; "Function"
0x180045f97  mov     [rsp+230h+var_1E8], rax
0x180045f9c  lea     rax, aSrbStatus; "SRB status"
0x180045fa3  mov     dword ptr [rsp+230h+var_1F0], r10d
0x180045fa8  mov     [rsp+230h+var_1F8], rax
0x180045fad  lea     rax, aSubFunction; "Sub function"
0x180045fb4  mov     dword ptr [rsp+230h+var_200], r11d
0x180045fb9  mov     [rsp+230h+var_208], rax
0x180045fbe  mov     rax, [r13+rbx*8+0]
0x180045fc3  mov     qword ptr [rsp+230h+var_210], rax
0x180045fc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045fcd  mov     rcx, [rbp+90h+var_40]
0x180045fd1  xor     rcx, rsp; StackCookie
0x180045fd4  call    __security_check_cookie
0x180045fd9  add     rsp, 200h
0x180045fe0  pop     r15
0x180045fe2  pop     r13
0x180045fe4  pop     r12
0x180045fe6  pop     rdi
0x180045fe7  pop     rsi
0x180045fe8  pop     rbx
0x180045fe9  pop     rbp
0x180045fea  retn
```
