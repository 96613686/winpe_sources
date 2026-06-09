# SC_PART_ENTRY::IsRecognized(void)

- ea: `0x1400031b0`
- end: `0x140003367`
- name: `?IsRecognized@SC_PART_ENTRY@@QEAAEXZ`
- size: `439`
- prototype: `unsigned __int8 __fastcall(SC_PART_ENTRY *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000f3b0`
- `0x140010d7c`
- `0x140013ba0`
- `0x140013e00`
- `0x140015900`

## callees

- `0x1400031b0`

## pseudocode

```c
unsigned __int8 __fastcall SC_PART_ENTRY::IsRecognized(SC_PART_ENTRY *this)
{
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx

  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this != 1 )
      return 0;
    v1 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_BSP_GUID.Data1;
    if ( !v1 )
      v1 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_BSP_GUID.Data4;
    if ( v1 )
    {
      v2 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_DPP_GUID.Data1;
      if ( !v2 )
        v2 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_DPP_GUID.Data4;
      if ( v2 )
      {
        v3 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
        if ( !v3 )
          v3 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
        if ( v3 )
        {
          v4 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_MAIN_OS_GUID.Data1;
          if ( !v4 )
            v4 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_MAIN_OS_GUID.Data4;
          if ( v4 )
          {
            v5 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1;
            if ( !v5 )
              v5 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4;
            if ( v5 )
            {
              v6 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_OS_DATA_GUID.Data1;
              if ( !v6 )
                v6 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_OS_DATA_GUID.Data4;
              if ( v6 )
              {
                v7 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_PRE_INSTALLED_GUID.Data1;
                if ( !v7 )
                  v7 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_PRE_INSTALLED_GUID.Data4;
                if ( v7 )
                {
                  v8 = *((_QWORD *)this + 4) - PARTITION_SERVICING_FILES_GUID;
                  if ( !v8 )
                    v8 = *((_QWORD *)this + 5) - 0x6A00C0A9EA8D4CAELL;
                  if ( v8 )
                  {
                    v9 = *((_QWORD *)this + 4) - PARTITION_SERVICING_METADATA_GUID;
                    if ( !v9 )
                      v9 = *((_QWORD *)this + 5) + 0x31D62D50C28FB145LL;
                    if ( v9 )
                    {
                      v10 = *((_QWORD *)this + 4) - PARTITION_SERVICING_RESERVE_GUID;
                      if ( !v10 )
                        v10 = *((_QWORD *)this + 5) - 0x146D13FEB6FF19A3LL;
                      if ( v10 )
                      {
                        v11 = *((_QWORD *)this + 4) - PARTITION_SERVICING_STAGING_ROOT_GUID;
                        if ( !v11 )
                          v11 = *((_QWORD *)this + 5) + 0x2046FB4244130C56LL;
                        if ( v11 )
                        {
                          v12 = *((_QWORD *)this + 4) - *(_QWORD *)&PARTITION_WINDOWS_SYSTEM_GUID.Data1;
                          if ( !v12 )
                            v12 = *((_QWORD *)this + 5) - *(_QWORD *)PARTITION_WINDOWS_SYSTEM_GUID.Data4;
                          if ( v12 )
                            return 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v14 = *((unsigned __int8 *)this + 32);
    if ( (unsigned __int8)v14 > 0x2Du || (v15 = 0x3F80000058D2LL, !_bittest64(&v15, v14)) )
    {
      if ( (_BYTE)v14 != 0xEF )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400031b0  mov     edx, [rcx]
0x1400031b2  test    edx, edx
0x1400031b4  jz      loc_140003343
0x1400031ba  cmp     edx, 1
0x1400031bd  jnz     loc_14000333F
0x1400031c3  mov     rax, [rcx+20h]
0x1400031c7  sub     rax, qword ptr cs:PARTITION_BSP_GUID.Data1
0x1400031ce  jnz     short loc_1400031DB
0x1400031d0  mov     rax, [rcx+28h]
0x1400031d4  sub     rax, qword ptr cs:PARTITION_BSP_GUID.Data4
0x1400031db  test    rax, rax
0x1400031de  jz      loc_14000335C
0x1400031e4  mov     rax, [rcx+20h]
0x1400031e8  sub     rax, qword ptr cs:PARTITION_DPP_GUID.Data1
0x1400031ef  jnz     short loc_1400031FC
0x1400031f1  mov     rax, [rcx+28h]
0x1400031f5  sub     rax, qword ptr cs:PARTITION_DPP_GUID.Data4
0x1400031fc  test    rax, rax
0x1400031ff  jz      loc_14000335C
0x140003205  mov     rax, [rcx+20h]
0x140003209  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x140003210  jnz     short loc_14000321D
0x140003212  mov     rax, [rcx+28h]
0x140003216  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x14000321d  test    rax, rax
0x140003220  jz      loc_14000335C
0x140003226  mov     rax, [rcx+20h]
0x14000322a  sub     rax, qword ptr cs:PARTITION_MAIN_OS_GUID.Data1
0x140003231  jnz     short loc_14000323E
0x140003233  mov     rax, [rcx+28h]
0x140003237  sub     rax, qword ptr cs:PARTITION_MAIN_OS_GUID.Data4
0x14000323e  test    rax, rax
0x140003241  jz      loc_14000335C
0x140003247  mov     rax, [rcx+20h]
0x14000324b  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x140003252  jnz     short loc_14000325F
0x140003254  mov     rax, [rcx+28h]
0x140003258  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x14000325f  test    rax, rax
0x140003262  jz      loc_14000335C
0x140003268  mov     rax, [rcx+20h]
0x14000326c  sub     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data1
0x140003273  jnz     short loc_140003280
0x140003275  mov     rax, [rcx+28h]
0x140003279  sub     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data4
0x140003280  test    rax, rax
0x140003283  jz      loc_14000335C
0x140003289  mov     rax, [rcx+20h]
0x14000328d  sub     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data1
0x140003294  jnz     short loc_1400032A1
0x140003296  mov     rax, [rcx+28h]
0x14000329a  sub     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data4
0x1400032a1  test    rax, rax
0x1400032a4  jz      loc_14000335C
0x1400032aa  mov     rax, [rcx+20h]
0x1400032ae  sub     rax, cs:PARTITION_SERVICING_FILES_GUID
0x1400032b5  jnz     short loc_1400032C2
0x1400032b7  mov     rax, [rcx+28h]
0x1400032bb  sub     rax, cs:qword_140007238
0x1400032c2  test    rax, rax
0x1400032c5  jz      loc_14000335C
0x1400032cb  mov     rax, [rcx+20h]
0x1400032cf  sub     rax, cs:PARTITION_SERVICING_METADATA_GUID
0x1400032d6  jnz     short loc_1400032E3
0x1400032d8  mov     rax, [rcx+28h]
0x1400032dc  sub     rax, cs:qword_140007248
0x1400032e3  test    rax, rax
0x1400032e6  jz      short loc_14000335C
0x1400032e8  mov     rax, [rcx+20h]
0x1400032ec  sub     rax, cs:PARTITION_SERVICING_RESERVE_GUID
0x1400032f3  jnz     short loc_140003300
0x1400032f5  mov     rax, [rcx+28h]
0x1400032f9  sub     rax, cs:qword_140007268
0x140003300  test    rax, rax
0x140003303  jz      short loc_14000335C
0x140003305  mov     rax, [rcx+20h]
0x140003309  sub     rax, cs:PARTITION_SERVICING_STAGING_ROOT_GUID
0x140003310  jnz     short loc_14000331D
0x140003312  mov     rax, [rcx+28h]
0x140003316  sub     rax, cs:qword_140007258
0x14000331d  test    rax, rax
0x140003320  jz      short loc_14000335C
0x140003322  mov     rdx, [rcx+20h]
0x140003326  sub     rdx, qword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data1
0x14000332d  jnz     short loc_14000333A
0x14000332f  mov     rdx, [rcx+28h]
0x140003333  sub     rdx, qword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data4
0x14000333a  test    rdx, rdx
0x14000333d  jz      short loc_14000335C
0x14000333f  xor     al, al
0x140003341  retn
0x140003343  movzx   edx, byte ptr [rcx+20h]
0x140003347  cmp     dl, 2Dh ; '-'
0x14000334a  ja      short loc_140003360
0x14000334c  mov     rcx, 3F80000058D2h
0x140003356  bt      rcx, rdx
0x14000335a  jnb     short loc_140003360
0x14000335c  mov     al, 1
0x14000335e  retn
0x140003360  cmp     dl, 0EFh
0x140003363  jnz     short loc_14000333F
0x140003365  jmp     short loc_14000335C
```
