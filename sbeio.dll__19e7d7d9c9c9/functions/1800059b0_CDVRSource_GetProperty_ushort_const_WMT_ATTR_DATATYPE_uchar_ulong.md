# CDVRSource::GetProperty(ushort const *,WMT_ATTR_DATATYPE *,uchar *,ulong *)

- ea: `0x1800059b0`
- end: `0x180005bee`
- name: `?GetProperty@CDVRSource@@UEAAJPEBGPEAW4WMT_ATTR_DATATYPE@@PEAEPEAK@Z`
- size: `574`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, const unsigned __int16 *, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000315c`
- `0x1800059b0`

## string_xrefs

- `0x180005b85`: `SeekReadAheadBufferTime`

## pseudocode

```c
__int64 __fastcall CDVRSource::GetProperty(
        HKEY *this,
        const unsigned __int16 *a2,
        enum WMT_ATTR_DATATYPE *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  const unsigned __int16 *v8; // rax
  int v9; // edi
  int v10; // r9d
  int v11; // ecx
  const unsigned __int16 *v12; // rax
  int v13; // r9d
  int v14; // r8d
  const unsigned __int16 *v15; // rax
  int v16; // r9d
  int v17; // r8d
  const unsigned __int16 *v18; // rax
  int v19; // r9d
  int v20; // r8d
  const unsigned __int16 *v21; // rax
  int v22; // r9d
  int v23; // r8d
  const unsigned __int16 *v24; // rax
  int v25; // r9d
  int v26; // r8d
  signed __int64 v27; // rax
  int v28; // r8d
  int v29; // ecx
  unsigned int RegDWORD; // eax

  if ( a5 && a4 && a3 )
  {
    if ( a2 != L"ReloadIndexOnSeek" )
    {
      v8 = a2;
      v9 = 2;
      do
      {
        v10 = *(const unsigned __int16 *)((char *)v8 + (char *)L"ReloadIndexOnSeek" - (char *)a2);
        v11 = *v8 - v10;
        if ( v11 )
          break;
        ++v8;
      }
      while ( v10 );
      if ( v11 )
      {
        if ( a2 == L"StreamNumIndexObjects" )
          goto LABEL_48;
        v12 = a2;
        do
        {
          v13 = *(const unsigned __int16 *)((char *)v12 + (char *)L"StreamNumIndexObjects" - (char *)a2);
          v14 = *v12 - v13;
          if ( v14 )
            break;
          ++v12;
        }
        while ( v13 );
        if ( !v14 )
        {
LABEL_48:
          if ( *a5 < 4 )
            return 2147942487LL;
          *(_DWORD *)a4 = 1;
        }
        else
        {
          if ( a2 == L"SourceBufferTime" )
            goto LABEL_44;
          v15 = a2;
          do
          {
            v16 = *(const unsigned __int16 *)((char *)v15 + (char *)L"SourceBufferTime" - (char *)a2);
            v17 = *v15 - v16;
            if ( v17 )
              break;
            ++v15;
          }
          while ( v16 );
          if ( !v17 )
          {
LABEL_44:
            if ( *a5 < 4 )
              return 2147942487LL;
            RegDWORD = GetRegDWORD(this[18], L"SeekReadAheadBufferTime", 5u);
            if ( RegDWORD > 2 )
              v9 = RegDWORD;
            *(_DWORD *)a4 = v9;
          }
          else
          {
            if ( a2 != L"SourceMaxBytesAtOnce" )
            {
              v18 = a2;
              do
              {
                v19 = *(const unsigned __int16 *)((char *)v18 + (char *)L"SourceMaxBytesAtOnce" - (char *)a2);
                v20 = *v18 - v19;
                if ( v20 )
                  break;
                ++v18;
              }
              while ( v19 );
              if ( v20 )
              {
                if ( a2 != L"FailSeekOnError" )
                {
                  v21 = a2;
                  do
                  {
                    v22 = *(const unsigned __int16 *)((char *)v21 + (char *)L"FailSeekOnError" - (char *)a2);
                    v23 = *v21 - v22;
                    if ( v23 )
                      break;
                    ++v21;
                  }
                  while ( v22 );
                  if ( v23 && a2 != L"PermitSeeksBeyondEndOfStream" )
                  {
                    v24 = a2;
                    do
                    {
                      v25 = *(const unsigned __int16 *)((char *)v24
                                                      + (char *)L"PermitSeeksBeyondEndOfStream"
                                                      - (char *)a2);
                      v26 = *v24 - v25;
                      if ( v26 )
                        break;
                      ++v24;
                    }
                    while ( v25 );
                    if ( v26 && a2 != L"UsePacketAtSeekPoint" )
                    {
                      v27 = (char *)L"UsePacketAtSeekPoint" - (char *)a2;
                      do
                      {
                        v28 = *(const unsigned __int16 *)((char *)a2 + v27);
                        v29 = *a2 - v28;
                        if ( v29 )
                          break;
                        ++a2;
                      }
                      while ( v28 );
                      if ( v29 )
                        return 2147500037LL;
                    }
                  }
                }
                if ( *a5 >= 4 )
                {
                  *(_DWORD *)a4 = 1;
LABEL_54:
                  *a3 = WMT_TYPE_BOOL;
                  goto LABEL_55;
                }
                return 2147942487LL;
              }
            }
            if ( *a5 < 4 )
              return 2147942487LL;
            *(_DWORD *)a4 = GetRegDWORD(this[18], L"MaxBytesAtOnce", 0xC800u);
          }
        }
        *a3 = WMT_TYPE_DWORD;
LABEL_55:
        *a5 = 4;
        return 0;
      }
    }
    if ( *a5 >= 4 )
    {
      *(_DWORD *)a4 = *((_DWORD *)this + 40) != 0;
      goto LABEL_54;
    }
    return 2147942487LL;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800059b0  push    rbx
0x1800059b2  push    rsi
0x1800059b3  push    rdi
0x1800059b4  push    r14
0x1800059b6  sub     rsp, 28h
0x1800059ba  mov     rbx, [rsp+48h+arg_20]
0x1800059bf  mov     rsi, r9
0x1800059c2  mov     r14, r8
0x1800059c5  mov     r10, rcx
0x1800059c8  test    rbx, rbx
0x1800059cb  jz      loc_180005BDF
0x1800059d1  test    r9, r9
0x1800059d4  jz      loc_180005BDF
0x1800059da  test    r8, r8
0x1800059dd  jz      loc_180005BDF
0x1800059e3  lea     r8, aReloadindexons; "ReloadIndexOnSeek"
0x1800059ea  cmp     rdx, r8
0x1800059ed  jz      loc_180005BB4
0x1800059f3  mov     rax, rdx
0x1800059f6  sub     r8, rdx
0x1800059f9  mov     edi, 2
0x1800059fe  movzx   ecx, word ptr [rax]
0x180005a01  movzx   r9d, word ptr [rax+r8]
0x180005a06  sub     ecx, r9d
0x180005a09  jnz     short loc_180005A13
0x180005a0b  add     rax, rdi
0x180005a0e  test    r9d, r9d
0x180005a11  jnz     short loc_1800059FE
0x180005a13  test    ecx, ecx
0x180005a15  jz      loc_180005BB4
0x180005a1b  lea     rcx, aStreamnumindex; "StreamNumIndexObjects"
0x180005a22  cmp     rdx, rcx
0x180005a25  jz      loc_180005BA0
0x180005a2b  mov     rax, rdx
0x180005a2e  sub     rcx, rdx
0x180005a31  movzx   r8d, word ptr [rax]
0x180005a35  movzx   r9d, word ptr [rax+rcx]
0x180005a3a  sub     r8d, r9d
0x180005a3d  jnz     short loc_180005A47
0x180005a3f  add     rax, rdi
0x180005a42  test    r9d, r9d
0x180005a45  jnz     short loc_180005A31
0x180005a47  test    r8d, r8d
0x180005a4a  jz      loc_180005BA0
0x180005a50  lea     rcx, aSourcebufferti; "SourceBufferTime"
0x180005a57  cmp     rdx, rcx
0x180005a5a  jz      loc_180005B79
0x180005a60  mov     rax, rdx
0x180005a63  sub     rcx, rdx
0x180005a66  movzx   r8d, word ptr [rax]
0x180005a6a  movzx   r9d, word ptr [rax+rcx]
0x180005a6f  sub     r8d, r9d
0x180005a72  jnz     short loc_180005A7C
0x180005a74  add     rax, rdi
0x180005a77  test    r9d, r9d
0x180005a7a  jnz     short loc_180005A66
0x180005a7c  test    r8d, r8d
0x180005a7f  jz      loc_180005B79
0x180005a85  lea     rcx, aSourcemaxbytes; "SourceMaxBytesAtOnce"
0x180005a8c  cmp     rdx, rcx
0x180005a8f  jz      loc_180005B57
0x180005a95  mov     rax, rdx
0x180005a98  sub     rcx, rdx
0x180005a9b  movzx   r8d, word ptr [rax]
0x180005a9f  movzx   r9d, word ptr [rax+rcx]
0x180005aa4  sub     r8d, r9d
0x180005aa7  jnz     short loc_180005AB1
0x180005aa9  add     rax, rdi
0x180005aac  test    r9d, r9d
0x180005aaf  jnz     short loc_180005A9B
0x180005ab1  test    r8d, r8d
0x180005ab4  jz      loc_180005B57
0x180005aba  lea     rcx, aFailseekonerro; "FailSeekOnError"
0x180005ac1  cmp     rdx, rcx
0x180005ac4  jz      loc_180005B4A
0x180005aca  mov     rax, rdx
0x180005acd  sub     rcx, rdx
0x180005ad0  movzx   r8d, word ptr [rax]
0x180005ad4  movzx   r9d, word ptr [rax+rcx]
0x180005ad9  sub     r8d, r9d
0x180005adc  jnz     short loc_180005AE6
0x180005ade  add     rax, rdi
0x180005ae1  test    r9d, r9d
0x180005ae4  jnz     short loc_180005AD0
0x180005ae6  test    r8d, r8d
0x180005ae9  jz      short loc_180005B4A
0x180005aeb  lea     rcx, aPermitseeksbey; "PermitSeeksBeyondEndOfStream"
0x180005af2  cmp     rdx, rcx
0x180005af5  jz      short loc_180005B4A
0x180005af7  mov     rax, rdx
0x180005afa  sub     rcx, rdx
0x180005afd  movzx   r8d, word ptr [rax]
0x180005b01  movzx   r9d, word ptr [rax+rcx]
0x180005b06  sub     r8d, r9d
0x180005b09  jnz     short loc_180005B13
0x180005b0b  add     rax, rdi
0x180005b0e  test    r9d, r9d
0x180005b11  jnz     short loc_180005AFD
0x180005b13  test    r8d, r8d
0x180005b16  jz      short loc_180005B4A
0x180005b18  lea     rax, aUsepacketatsee; "UsePacketAtSeekPoint"
0x180005b1f  cmp     rdx, rax
0x180005b22  jz      short loc_180005B4A
0x180005b24  sub     rax, rdx
0x180005b27  movzx   ecx, word ptr [rdx]
0x180005b2a  movzx   r8d, word ptr [rdx+rax]
0x180005b2f  sub     ecx, r8d
0x180005b32  jnz     short loc_180005B3C
0x180005b34  add     rdx, rdi
0x180005b37  test    r8d, r8d
0x180005b3a  jnz     short loc_180005B27
0x180005b3c  test    ecx, ecx
0x180005b3e  jz      short loc_180005B4A
0x180005b40  mov     eax, 80004005h
0x180005b45  jmp     loc_180005BE4
0x180005b4a  cmp     dword ptr [rbx], 4
0x180005b4d  jb      short loc_180005BB9
0x180005b4f  mov     dword ptr [rsi], 1
0x180005b55  jmp     short loc_180005BCE
0x180005b57  cmp     dword ptr [rbx], 4
0x180005b5a  jb      short loc_180005BB9
0x180005b5c  mov     rcx, [r10+90h]; hKey
0x180005b63  lea     rdx, ValueName; "MaxBytesAtOnce"
0x180005b6a  mov     r8d, 0C800h; unsigned int
0x180005b70  call    ?GetRegDWORD@@YAKPEAUHKEY__@@PEBGK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong)
0x180005b75  mov     [rsi], eax
0x180005b77  jmp     short loc_180005BAB
0x180005b79  cmp     dword ptr [rbx], 4
0x180005b7c  jb      short loc_180005BB9
0x180005b7e  mov     rcx, [r10+90h]; hKey
0x180005b85  lea     rdx, aSeekreadaheadb; "SeekReadAheadBufferTime"
0x180005b8c  mov     r8d, 5; unsigned int
0x180005b92  call    ?GetRegDWORD@@YAKPEAUHKEY__@@PEBGK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong)
0x180005b97  cmp     eax, edi
0x180005b99  cmova   edi, eax
0x180005b9c  mov     [rsi], edi
0x180005b9e  jmp     short loc_180005BAB
0x180005ba0  cmp     dword ptr [rbx], 4
0x180005ba3  jb      short loc_180005BB9
0x180005ba5  mov     dword ptr [rsi], 1
0x180005bab  mov     dword ptr [r14], 0
0x180005bb2  jmp     short loc_180005BD5
0x180005bb4  cmp     dword ptr [rbx], 4
0x180005bb7  jnb     short loc_180005BC0
0x180005bb9  mov     eax, 80070057h
0x180005bbe  jmp     short loc_180005BE4
0x180005bc0  xor     eax, eax
0x180005bc2  cmp     [r10+0A0h], eax
0x180005bc9  setnz   al
0x180005bcc  mov     [rsi], eax
0x180005bce  mov     dword ptr [r14], 3
0x180005bd5  mov     dword ptr [rbx], 4
0x180005bdb  xor     eax, eax
0x180005bdd  jmp     short loc_180005BE4
0x180005bdf  mov     eax, 80004003h
0x180005be4  add     rsp, 28h
0x180005be8  pop     r14
0x180005bea  pop     rdi
0x180005beb  pop     rsi
0x180005bec  pop     rbx
0x180005bed  retn
```
