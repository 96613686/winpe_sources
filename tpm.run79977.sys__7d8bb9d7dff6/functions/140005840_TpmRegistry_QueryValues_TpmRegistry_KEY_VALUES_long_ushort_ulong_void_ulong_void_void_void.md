# TpmRegistry::QueryValues(TpmRegistry::KEY_VALUES,long (*)(ushort *,ulong,void *,ulong,void *,void *),void *)

- ea: `0x140005840`
- end: `0x140005964`
- name: `?QueryValues@TpmRegistry@@SAJW4KEY_VALUES@1@P6AJPEAGKPEAXK22@Z2@Z`
- size: `292`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005698`
- `0x140006300`
- `0x1400211dc`

## callees

- `0x140005840`
- `0x140009278`
- `0x14000a0a4`
- `0x14000a164`
- `0x140039840`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140005932`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140005932`

## pseudocode

```c
__int64 __fastcall TpmRegistry::QueryValues(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // esi
  unsigned __int8 *v6; // rdi
  int inited; // ebx
  unsigned __int8 *v8; // rax
  void *Src[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v11; // [rsp+40h] [rbp-49h] BYREF
  int v12; // [rsp+48h] [rbp-41h]
  _BYTE v13[100]; // [rsp+4Ch] [rbp-3Dh] BYREF
  unsigned __int64 retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v15; // [rsp+108h] [rbp+7Fh] BYREF

  v15 = 0;
  *(_OWORD *)Src = 0;
  v5 = a1;
  v6 = 0;
  inited = TpmRegistry::OpenKey(a1, 131097, &v15);
  if ( !inited )
  {
    memset(v13, 0, sizeof(v13));
    v11 = a2;
    v12 = 16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, v5);
    inited = TpmRegistry::InitRegistryKey(Src, v5);
    if ( inited >= 0 )
    {
      v8 = TpmAlloc(1, LOWORD(Src[0]) + 2LL, retaddr);
      v6 = v8;
      if ( v8 )
      {
        memmove(v8, Src[1], LOWORD(Src[0]));
        *(_WORD *)&v6[2 * ((unsigned __int64)LOWORD(Src[0]) >> 1)] = 0;
        inited = RtlQueryRegistryValuesEx(0, v6, &v11, a3, 0);
      }
      else
      {
        inited = -1073741670;
      }
    }
  }
  TpmFree(Src[1]);
  TpmFree(v6);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140005840  push    rbp
0x140005842  push    rbx
0x140005843  push    rsi
0x140005844  push    rdi
0x140005845  push    r14
0x140005847  push    r15
0x140005849  lea     rbp, [rsp-2Fh]
0x14000584e  sub     rsp, 0B8h
0x140005855  mov     r15, r8
0x140005858  mov     [rbp+57h+arg_18], 0
0x140005860  mov     r14, rdx
0x140005863  lea     r8, [rbp+57h+arg_18]
0x140005867  xorps   xmm0, xmm0
0x14000586a  mov     edx, 20019h
0x14000586f  movups  xmmword ptr [rbp+57h+Src], xmm0
0x140005873  mov     esi, ecx
0x140005875  xor     edi, edi
0x140005877  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x14000587c  mov     ebx, eax
0x14000587e  test    eax, eax
0x140005880  jnz     loc_140005940
0x140005886  xor     edx, edx; Val
0x140005888  lea     r8d, [rdi+64h]; Size
0x14000588c  lea     rcx, [rbp+57h+var_94]; void *
0x140005890  call    memset
0x140005895  mov     [rbp+57h+var_A0], r14
0x140005899  mov     [rbp+57h+var_98], 10h
0x1400058a0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400058a7  lea     rax, WPP_GLOBAL_Control
0x1400058ae  cmp     rcx, rax
0x1400058b1  jz      short loc_1400058D0
0x1400058b3  mov     eax, [rcx+2Ch]
0x1400058b6  test    al, 4
0x1400058b8  jz      short loc_1400058D0
0x1400058ba  mov     rcx, [rcx+18h]
0x1400058be  lea     edx, [rdi+1Ch]
0x1400058c1  mov     r9d, esi
0x1400058c4  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x1400058cb  call    WPP_SF_d
0x1400058d0  mov     edx, esi
0x1400058d2  lea     rcx, [rbp+57h+Src]
0x1400058d6  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)
0x1400058db  mov     ebx, eax
0x1400058dd  test    eax, eax
0x1400058df  js      short loc_140005940
0x1400058e1  movzx   edx, word ptr [rbp+57h+Src]
0x1400058e5  mov     cl, 1; bool
0x1400058e7  mov     r8, [rbp+5Fh]; unsigned __int64
0x1400058eb  add     rdx, 2; unsigned __int64
0x1400058ef  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x1400058f4  mov     rdi, rax
0x1400058f7  test    rax, rax
0x1400058fa  jnz     short loc_140005903
0x1400058fc  mov     ebx, 0C000009Ah
0x140005901  jmp     short loc_140005940
0x140005903  movzx   r8d, word ptr [rbp+57h+Src]; Size
0x140005908  mov     rcx, rdi; void *
0x14000590b  mov     rdx, [rbp+57h+Src+8]; Src
0x14000590f  call    memmove
0x140005914  movzx   ecx, word ptr [rbp+57h+Src]
0x140005918  lea     r8, [rbp+57h+var_A0]
0x14000591c  shr     rcx, 1
0x14000591f  xor     eax, eax
0x140005921  mov     r9, r15
0x140005924  mov     [rsp+0E0h+var_C0], rax
0x140005929  mov     rdx, rdi
0x14000592c  mov     [rdi+rcx*2], ax
0x140005930  xor     ecx, ecx
0x140005932  call    cs:__imp_RtlQueryRegistryValuesEx
0x140005939  nop     dword ptr [rax+rax+00h]
0x14000593e  mov     ebx, eax
0x140005940  mov     rcx, [rbp+57h+Src+8]; void *
0x140005944  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140005949  mov     rcx, rdi; void *
0x14000594c  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140005951  mov     eax, ebx
0x140005953  add     rsp, 0B8h
0x14000595a  pop     r15
0x14000595c  pop     r14
0x14000595e  pop     rdi
0x14000595f  pop     rsi
0x140005960  pop     rbx
0x140005961  pop     rbp
0x140005962  retn
```
