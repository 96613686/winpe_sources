# RpcpBindRpc

- ea: `0x180005630`
- end: `0x18000592c`
- name: `RpcpBindRpc`
- size: `764`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016288`
- `0x1800163d0`

## callees

- `0x180005630`
- `0x180005940`
- `0x180006620`
- `0x180006eb6`
- `0x180017929`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005720`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005786`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005720`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005896`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005896`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057c2`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000588b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000588b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800058af`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800058af`
- `RPCRT4!RpcStringFreeW` at `0x1800058bc`
- `RPCRT4!RpcStringFreeW` at `0x1800058bc`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  char *v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned __int16 *v9; // rbp
  unsigned __int16 *v10; // rax
  WCHAR *v11; // rax
  wchar_t *v12; // rsi
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  const wchar_t *v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned __int16 *v19; // r10
  unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  RPC_STATUS v22; // ebx
  RPC_STATUS v23; // ebx
  int v24; // ecx
  DWORD nSize; // [rsp+30h] [rbp-68h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-60h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-58h] BYREF

  String = 0;
  v5 = Src;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !Src )
    goto LABEL_27;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&Src[2 * v7] );
  if ( !*(_WORD *)Src )
    goto LABEL_27;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return 3221225762LL;
    v7 -= 2LL;
    if ( !v7 )
      return 3221225762LL;
    v9 = (unsigned __int16 *)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_28;
    v5 = Src + 4;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return 3221225495LL;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
      {
LABEL_27:
        v9 = 0;
LABEL_28:
        v14 = (unsigned __int16 *)LocalAlloc(0, 0x18u);
        v15 = v14;
        if ( v14 )
        {
          v16 = L"\\PIPE\\";
          v17 = 12;
          v18 = 2147483646;
          v19 = v14;
          do
          {
            if ( !v18 )
              break;
            if ( !*v16 )
              break;
            *v19++ = *v16++;
            --v18;
            --v17;
          }
          while ( v17 );
          v20 = v19 - 1;
          if ( v17 )
            v20 = v19;
          *v20 = 0;
          if ( !v17 )
            goto LABEL_49;
          v21 = 12;
          do
          {
            if ( !*v14 )
              break;
            ++v14;
            --v21;
          }
          while ( v21 );
          if ( v21 && (int)RtlStringCopyWorkerW(&v15[12 - v21], v21, v21, L"samr") >= 0 )
          {
            v22 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", v9, v15, 0, &String);
            LocalFree(v15);
            if ( v22 )
            {
              v13 = -1073741801;
            }
            else
            {
              v23 = RpcBindingFromStringBindingW(String, a4);
              RpcStringFreeW(&String);
              if ( v23 )
              {
                *a4 = 0;
                v24 = -1073741534;
                if ( (unsigned int)(v23 - 1706) > 1 )
                  v24 = -1073741801;
                v13 = v24;
              }
              else
              {
                v13 = 0;
              }
            }
          }
          else
          {
LABEL_49:
            LocalFree(v15);
            v13 = -1073741811;
          }
        }
        else
        {
          v13 = -1073741801;
        }
        goto LABEL_50;
      }
    }
  }
  if ( *(_WORD *)&v5[2 * v7 - 2] == 46 )
    --v7;
  v11 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v12 = v11;
  if ( v11 )
  {
    nSize = 261;
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v11, &nSize)
      && v7 == nSize
      && !wcsnicmp(v12, (const wchar_t *)v5, v7) )
    {
      v9 = 0;
    }
    LocalFree(v12);
    goto LABEL_28;
  }
  v13 = -1073741801;
LABEL_50:
  if ( v6 )
    LocalFree(v6);
  return v13;
}

```

## disassembly

```asm
0x180005630  mov     [rsp+arg_8], rbx
0x180005635  mov     [rsp+arg_10], rbp
0x18000563a  push    rsi
0x18000563b  push    rdi
0x18000563c  push    r12
0x18000563e  push    r14
0x180005640  push    r15
0x180005642  sub     rsp, 70h
0x180005646  mov     rax, cs:__security_cookie
0x18000564d  xor     rax, rsp
0x180005650  mov     [rsp+98h+var_38], rax
0x180005655  xor     r12d, r12d
0x180005658  mov     r15, r9
0x18000565b  mov     [rsp+98h+String], r12
0x180005660  mov     rdi, rcx
0x180005663  mov     [rsp+98h+nSize], r12d
0x180005668  mov     r14d, r12d
0x18000566b  mov     [r9], r12
0x18000566e  test    rcx, rcx
0x180005671  jz      loc_1800057B8
0x180005677  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000567e  xchg    ax, ax
0x180005680  inc     rbx
0x180005683  cmp     [rcx+rbx*2], r12w
0x180005688  jnz     short loc_180005680
0x18000568a  movzx   eax, word ptr [rcx]
0x18000568d  test    ax, ax
0x180005690  jz      loc_1800057B8
0x180005696  cmp     ax, 5Ch ; '\'
0x18000569a  jnz     short loc_1800056C7
0x18000569c  cmp     [rcx+2], ax
0x1800056a0  jnz     short loc_1800056A8
0x1800056a2  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800056a6  jnz     short loc_1800056B2
0x1800056a8  mov     eax, 0C0000122h
0x1800056ad  jmp     loc_180005906
0x1800056b2  lea     rax, [rcx+4]
0x1800056b6  mov     rbp, rdi
0x1800056b9  test    rax, rax
0x1800056bc  jz      loc_1800057BB
0x1800056c2  mov     rdi, rax
0x1800056c5  jmp     short loc_180005706
0x1800056c7  lea     rdx, ds:6[rbx*2]; uBytes
0x1800056cf  xor     ecx, ecx; uFlags
0x1800056d1  call    cs:__imp_LocalAlloc
0x1800056d7  mov     r14, rax
0x1800056da  test    rax, rax
0x1800056dd  jnz     short loc_1800056E9
0x1800056df  mov     eax, 0C0000017h
0x1800056e4  jmp     loc_180005906
0x1800056e9  lea     r8, ds:2[rbx*2]; Size
0x1800056f1  mov     dword ptr [rax], 5C005Ch
0x1800056f7  lea     rcx, [rax+4]; void *
0x1800056fb  mov     rdx, rdi; Src
0x1800056fe  call    memcpy_0
0x180005703  mov     rbp, r14
0x180005706  cmp     rbx, 0Fh
0x18000570a  ja      short loc_180005747
0x18000570c  lea     r8, [rsp+98h+nSize]; nSize
0x180005711  mov     [rsp+98h+nSize], 10h
0x180005719  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x18000571e  xor     ecx, ecx; NameType
0x180005720  call    cs:__imp_GetComputerNameExW
0x180005726  test    eax, eax
0x180005728  jz      short loc_180005747
0x18000572a  mov     eax, [rsp+98h+nSize]
0x18000572e  cmp     rbx, rax
0x180005731  jnz     short loc_180005747
0x180005733  mov     r8, rbx; MaxCount
0x180005736  lea     rcx, [rsp+98h+Buffer]; String1
0x18000573b  mov     rdx, rdi; String2
0x18000573e  call    _wcsnicmp
0x180005743  test    eax, eax
0x180005745  jz      short loc_1800057B8
0x180005747  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x18000574d  jnz     short loc_180005752
0x18000574f  dec     rbx
0x180005752  mov     edx, 20Ah; uBytes
0x180005757  xor     ecx, ecx; uFlags
0x180005759  call    cs:__imp_LocalAlloc
0x18000575f  mov     rsi, rax
0x180005762  test    rax, rax
0x180005765  jnz     short loc_180005771
0x180005767  mov     ebx, 0C0000017h
0x18000576c  jmp     loc_1800058F6
0x180005771  lea     r8, [rsp+98h+nSize]; nSize
0x180005776  mov     [rsp+98h+nSize], 105h
0x18000577e  mov     rdx, rsi; lpBuffer
0x180005781  mov     ecx, 3; NameType
0x180005786  call    cs:__imp_GetComputerNameExW
0x18000578c  test    eax, eax
0x18000578e  jz      short loc_1800057AD
0x180005790  mov     eax, [rsp+98h+nSize]
0x180005794  cmp     rbx, rax
0x180005797  jnz     short loc_1800057AD
0x180005799  mov     r8, rbx; MaxCount
0x18000579c  mov     rdx, rdi; String2
0x18000579f  mov     rcx, rsi; String1
0x1800057a2  call    _wcsnicmp
0x1800057a7  test    eax, eax
0x1800057a9  cmovz   rbp, r12
0x1800057ad  mov     rcx, rsi; hMem
0x1800057b0  call    cs:__imp_LocalFree
0x1800057b6  jmp     short loc_1800057BB
0x1800057b8  mov     rbp, r12
0x1800057bb  mov     edx, 18h; uBytes
0x1800057c0  xor     ecx, ecx; uFlags
0x1800057c2  call    cs:__imp_LocalAlloc
0x1800057c8  mov     rdi, rax
0x1800057cb  test    rax, rax
0x1800057ce  jnz     short loc_1800057DA
0x1800057d0  mov     ebx, 0C0000017h
0x1800057d5  jmp     loc_1800058F6
0x1800057da  mov     r11d, 0Ch
0x1800057e0  lea     r8, aPipe; "\\PIPE\\"
0x1800057e7  mov     r9d, r11d
0x1800057ea  mov     edx, 7FFFFFFEh
0x1800057ef  mov     r10, rdi
0x1800057f2  test    rdx, rdx
0x1800057f5  jz      short loc_180005815
0x1800057f7  movzx   eax, word ptr [r8]
0x1800057fb  test    ax, ax
0x1800057fe  jz      short loc_180005815
0x180005800  mov     [r10], ax
0x180005804  add     r8, 2
0x180005808  add     r10, 2
0x18000580c  dec     rdx
0x18000580f  sub     r9, 1
0x180005813  jnz     short loc_1800057F2
0x180005815  test    r9, r9
0x180005818  lea     rdx, [r10-2]
0x18000581c  cmovnz  rdx, r10
0x180005820  mov     [rdx], r12w
0x180005824  jz      loc_1800058E8
0x18000582a  mov     r8, r11
0x18000582d  mov     rax, rdi
0x180005830  cmp     [rax], r12w
0x180005834  jz      short loc_180005840
0x180005836  add     rax, 2
0x18000583a  sub     r8, 1
0x18000583e  jnz     short loc_180005830
0x180005840  mov     rcx, r11
0x180005843  sub     rcx, r8
0x180005846  test    r8, r8
0x180005849  cmovz   rcx, r12
0x18000584d  jz      loc_1800058E8
0x180005853  sub     r11, rcx
0x180005856  lea     r9, aSamr; "samr"
0x18000585d  mov     rdx, r11
0x180005860  lea     rcx, [rdi+rcx*2]
0x180005864  call    RtlStringCopyWorkerW
0x180005869  test    eax, eax
0x18000586b  js      short loc_1800058E8
0x18000586d  lea     rax, [rsp+98h+String]
0x180005872  mov     r9, rdi; Endpoint
0x180005875  mov     [rsp+98h+StringBinding], rax; StringBinding
0x18000587a  lea     rdx, ProtSeq; "ncacn_np"
0x180005881  mov     r8, rbp; NetworkAddr
0x180005884  mov     [rsp+98h+Options], r12; Options
0x180005889  xor     ecx, ecx; ObjUuid
0x18000588b  call    cs:__imp_RpcStringBindingComposeW
0x180005891  mov     rcx, rdi; hMem
0x180005894  mov     ebx, eax
0x180005896  call    cs:__imp_LocalFree
0x18000589c  test    ebx, ebx
0x18000589e  jz      short loc_1800058A7
0x1800058a0  mov     ebx, 0C0000017h
0x1800058a5  jmp     short loc_1800058F6
0x1800058a7  mov     rcx, [rsp+98h+String]; StringBinding
0x1800058ac  mov     rdx, r15; Binding
0x1800058af  call    cs:__imp_RpcBindingFromStringBindingW
0x1800058b5  lea     rcx, [rsp+98h+String]; String
0x1800058ba  mov     ebx, eax
0x1800058bc  call    cs:__imp_RpcStringFreeW
0x1800058c2  test    ebx, ebx
0x1800058c4  jz      short loc_1800058E3
0x1800058c6  lea     eax, [rbx-6AAh]
0x1800058cc  mov     [r15], r12
0x1800058cf  mov     ebx, 0C0000017h
0x1800058d4  cmp     eax, 1
0x1800058d7  mov     ecx, 0C0000122h
0x1800058dc  cmova   ecx, ebx
0x1800058df  mov     ebx, ecx
0x1800058e1  jmp     short loc_1800058F6
0x1800058e3  mov     ebx, r12d
0x1800058e6  jmp     short loc_1800058F6
0x1800058e8  mov     rcx, rdi; hMem
0x1800058eb  call    cs:__imp_LocalFree
0x1800058f1  mov     ebx, 0C000000Dh
0x1800058f6  test    r14, r14
0x1800058f9  jz      short loc_180005904
0x1800058fb  mov     rcx, r14; hMem
0x1800058fe  call    cs:__imp_LocalFree
0x180005904  mov     eax, ebx
0x180005906  mov     rcx, [rsp+98h+var_38]
0x18000590b  xor     rcx, rsp; StackCookie
0x18000590e  call    __security_check_cookie
0x180005913  lea     r11, [rsp+98h+var_28]
0x180005918  mov     rbx, [r11+38h]
0x18000591c  mov     rbp, [r11+40h]
0x180005920  mov     rsp, r11
0x180005923  pop     r15
0x180005925  pop     r14
0x180005927  pop     r12
0x180005929  pop     rdi
0x18000592a  pop     rsi
0x18000592b  retn
```
