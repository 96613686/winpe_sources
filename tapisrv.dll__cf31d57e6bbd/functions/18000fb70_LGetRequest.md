# LGetRequest

- ea: `0x18000fb70`
- end: `0x18000fdba`
- name: `LGetRequest`
- size: `586`
- prototype: `void __fastcall(__int64, _DWORD *, unsigned int, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x18000fb70`
- `0x18001f514`
- `0x18002c8d4`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fbeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fbeb`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd3c`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd80`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd3c`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd80`
- `KERNEL32!EnterCriticalSection` at `0x18000fbcd`
- `KERNEL32!EnterCriticalSection` at `0x18000fbcd`

## string_xrefs

- `0x18000fce6`: `   Comment: [%ls]`

## pseudocode

```c
void __fastcall LGetRequest(__int64 a1, _DWORD *a2, unsigned int a3, _OWORD *a4, _DWORD *a5)
{
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rbp
  __int64 v10; // rcx
  _OWORD *v11; // rax
  __int128 v12; // xmm1

  if ( a3 >= 0x1E0 )
  {
    v7 = WaitForExclusiveLineAppAccess((unsigned int)a2[2], a1);
    v8 = v7;
    if ( v7 )
    {
      if ( a2[3] == 1 )
      {
        if ( *(_QWORD *)(v7 + 56) )
        {
          EnterCriticalSection(&gPriorityListCritSec);
          if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v8 + 208), *(_QWORD *)(*(_QWORD *)qword_180051940 + 208LL))
            || (v9 = (wchar_t *)lpMem) == 0 )
          {
            *a2 = -2147483579;
          }
          else
          {
            v10 = 3;
            v11 = lpMem;
            do
            {
              *a4 = *v11;
              a4[1] = v11[1];
              a4[2] = v11[2];
              a4[3] = v11[3];
              a4[4] = v11[4];
              a4[5] = v11[5];
              a4[6] = v11[6];
              v12 = v11[7];
              v11 += 8;
              a4[7] = v12;
              a4 += 8;
              --v10;
            }
            while ( v10 );
            *a4 = *v11;
            a4[1] = v11[1];
            a4[2] = v11[2];
            a4[3] = v11[3];
            a4[4] = v11[4];
            a4[5] = v11[5];
            TRACELogPrint(262146, "Getting request:  0x%p", v9);
            TRACELogPrint(262146, "   DestAddress: [%ls]", v9);
            TRACELogPrint(262146, "   AppName: [%ls]", v9 + 80);
            TRACELogPrint(262146, "   CalledParty: [%ls]", v9 + 120);
            TRACELogPrint(262146, "   Comment: [%ls]", v9 + 160);
            a2[4] = 0;
            a2[5] = 480;
            *a5 = 540;
            lpMem = (LPVOID)*((_QWORD *)v9 + 60);
            if ( !lpMem )
              qword_180051950 = 0;
            ServerFree(v9);
          }
          LeaveCriticalSection(&gPriorityListCritSec);
        }
        else
        {
          *a2 = -2147483577;
        }
      }
      else if ( a2[3] == 2 )
      {
        *a2 = *(_DWORD *)(v7 + 52) != 0 ? -2147483579 : -2147483577;
      }
      else
      {
        *a2 = -2147483592;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v8 >> 4)));
    }
    else
    {
      *a2 = dword_180051918 != 0 ? -2147483628 : -2147483568;
    }
    TRACELogPrint(524290, "lineGetRequest: exit, result=x%x", *a2);
  }
  else
  {
    *a2 = -2147483576;
  }
}

```

## disassembly

```asm
0x18000fb70  push    rbx
0x18000fb72  push    rbp
0x18000fb73  push    rsi
0x18000fb74  push    rdi
0x18000fb75  sub     rsp, 28h
0x18000fb79  mov     rsi, r9
0x18000fb7c  mov     rbx, rdx
0x18000fb7f  cmp     r8d, 1E0h
0x18000fb86  jnb     short loc_18000FB93
0x18000fb88  mov     dword ptr [rdx], 80000048h
0x18000fb8e  jmp     loc_18000FDB1
0x18000fb93  mov     rdx, rcx
0x18000fb96  mov     ecx, [rbx+8]
0x18000fb99  call    WaitForExclusiveLineAppAccess
0x18000fb9e  mov     rdi, rax
0x18000fba1  test    rax, rax
0x18000fba4  jz      loc_18000FD88
0x18000fbaa  cmp     dword ptr [rbx+0Ch], 1
0x18000fbae  jnz     loc_18000FD44
0x18000fbb4  cmp     qword ptr [rax+38h], 0
0x18000fbb9  jnz     short loc_18000FBC6
0x18000fbbb  mov     dword ptr [rbx], 80000047h
0x18000fbc1  jmp     loc_18000FD64
0x18000fbc6  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18000fbcd  call    cs:__imp_EnterCriticalSection
0x18000fbd3  mov     rax, cs:qword_180051940
0x18000fbda  mov     rcx, [rdi+0D0h]
0x18000fbe1  mov     rdx, [rax]
0x18000fbe4  mov     rdx, [rdx+0D0h]
0x18000fbeb  call    cs:__imp__o__wcsicmp
0x18000fbf1  test    eax, eax
0x18000fbf3  jnz     loc_18000FD2F
0x18000fbf9  mov     rbp, cs:lpMem
0x18000fc00  test    rbp, rbp
0x18000fc03  jz      loc_18000FD2F
0x18000fc09  mov     ecx, 3
0x18000fc0e  mov     rax, rbp
0x18000fc11  lea     edx, [rcx+7Dh]
0x18000fc14  movups  xmm0, xmmword ptr [rax]
0x18000fc17  movups  xmmword ptr [rsi], xmm0
0x18000fc1a  movups  xmm1, xmmword ptr [rax+10h]
0x18000fc1e  movups  xmmword ptr [rsi+10h], xmm1
0x18000fc22  movups  xmm0, xmmword ptr [rax+20h]
0x18000fc26  movups  xmmword ptr [rsi+20h], xmm0
0x18000fc2a  movups  xmm1, xmmword ptr [rax+30h]
0x18000fc2e  movups  xmmword ptr [rsi+30h], xmm1
0x18000fc32  movups  xmm0, xmmword ptr [rax+40h]
0x18000fc36  movups  xmmword ptr [rsi+40h], xmm0
0x18000fc3a  movups  xmm1, xmmword ptr [rax+50h]
0x18000fc3e  movups  xmmword ptr [rsi+50h], xmm1
0x18000fc42  movups  xmm0, xmmword ptr [rax+60h]
0x18000fc46  movups  xmmword ptr [rsi+60h], xmm0
0x18000fc4a  movups  xmm1, xmmword ptr [rax+70h]
0x18000fc4e  add     rax, rdx
0x18000fc51  movups  xmmword ptr [rsi+70h], xmm1
0x18000fc55  add     rsi, rdx
0x18000fc58  sub     rcx, 1
0x18000fc5c  jnz     short loc_18000FC14
0x18000fc5e  movups  xmm0, xmmword ptr [rax]
0x18000fc61  mov     r8, rbp
0x18000fc64  lea     rdx, aGettingRequest; "Getting request:  0x%p"
0x18000fc6b  movups  xmmword ptr [rsi], xmm0
0x18000fc6e  movups  xmm1, xmmword ptr [rax+10h]
0x18000fc72  movups  xmmword ptr [rsi+10h], xmm1
0x18000fc76  movups  xmm0, xmmword ptr [rax+20h]
0x18000fc7a  movups  xmmword ptr [rsi+20h], xmm0
0x18000fc7e  movups  xmm1, xmmword ptr [rax+30h]
0x18000fc82  movups  xmmword ptr [rsi+30h], xmm1
0x18000fc86  movups  xmm0, xmmword ptr [rax+40h]
0x18000fc8a  movups  xmmword ptr [rsi+40h], xmm0
0x18000fc8e  movups  xmm1, xmmword ptr [rax+50h]
0x18000fc92  movups  xmmword ptr [rsi+50h], xmm1
0x18000fc96  mov     esi, 40002h
0x18000fc9b  mov     ecx, esi
0x18000fc9d  call    TRACELogPrint
0x18000fca2  mov     r8, rbp
0x18000fca5  lea     rdx, aDestaddressLs; "   DestAddress: [%ls]"
0x18000fcac  mov     ecx, esi
0x18000fcae  call    TRACELogPrint
0x18000fcb3  lea     r8, [rbp+0A0h]
0x18000fcba  mov     ecx, esi
0x18000fcbc  lea     rdx, aAppnameLs; "   AppName: [%ls]"
0x18000fcc3  call    TRACELogPrint
0x18000fcc8  lea     r8, [rbp+0F0h]
0x18000fccf  mov     ecx, esi
0x18000fcd1  lea     rdx, aCalledpartyLs; "   CalledParty: [%ls]"
0x18000fcd8  call    TRACELogPrint
0x18000fcdd  lea     r8, [rbp+140h]
0x18000fce4  mov     ecx, esi
0x18000fce6  lea     rdx, aCommentLs; "   Comment: [%ls]"
0x18000fced  call    TRACELogPrint
0x18000fcf2  mov     rax, [rsp+48h+arg_20]
0x18000fcf7  mov     dword ptr [rbx+10h], 0
0x18000fcfe  mov     dword ptr [rbx+14h], 1E0h
0x18000fd05  mov     dword ptr [rax], 21Ch
0x18000fd0b  mov     rax, [rbp+1E0h]
0x18000fd12  mov     cs:lpMem, rax
0x18000fd19  test    rax, rax
0x18000fd1c  jnz     short loc_18000FD25
0x18000fd1e  mov     cs:qword_180051950, rax
0x18000fd25  mov     rcx, rbp; lpMem
0x18000fd28  call    ServerFree
0x18000fd2d  jmp     short loc_18000FD35
0x18000fd2f  mov     dword ptr [rbx], 80000045h
0x18000fd35  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18000fd3c  call    cs:__imp_LeaveCriticalSection
0x18000fd42  jmp     short loc_18000FD64
0x18000fd44  cmp     dword ptr [rbx+0Ch], 2
0x18000fd48  jnz     short loc_18000FD5E
0x18000fd4a  mov     eax, [rax+34h]
0x18000fd4d  neg     eax
0x18000fd4f  sbb     ecx, ecx
0x18000fd51  and     ecx, 0FFFFFFFEh
0x18000fd54  add     ecx, 80000047h
0x18000fd5a  mov     [rbx], ecx
0x18000fd5c  jmp     short loc_18000FD64
0x18000fd5e  mov     dword ptr [rbx], 80000038h
0x18000fd64  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000fd6a  shr     rdi, 4
0x18000fd6e  and     rdi, rax
0x18000fd71  mov     rax, cs:gLockTable
0x18000fd78  lea     rcx, [rdi+rdi*4]
0x18000fd7c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000fd80  call    cs:__imp_LeaveCriticalSection
0x18000fd86  jmp     short loc_18000FD9D
0x18000fd88  mov     eax, cs:dword_180051918
0x18000fd8e  neg     eax
0x18000fd90  sbb     ecx, ecx
0x18000fd92  and     ecx, 0FFFFFFC4h
0x18000fd95  add     ecx, 80000050h
0x18000fd9b  mov     [rbx], ecx
0x18000fd9d  mov     r8d, [rbx]
0x18000fda0  lea     rdx, aLinegetrequest; "lineGetRequest: exit, result=x%x"
0x18000fda7  mov     ecx, 80002h
0x18000fdac  call    TRACELogPrint
0x18000fdb1  add     rsp, 28h
0x18000fdb5  pop     rdi
0x18000fdb6  pop     rsi
0x18000fdb7  pop     rbp
0x18000fdb8  pop     rbx
0x18000fdb9  retn
```
