# SampLookupIdsInDomain(void *,ulong,ulong *,_UNICODE_STRING * *,_SID_NAME_USE * *)

- ea: `0x18000ad50`
- end: `0x18000b009`
- name: `?SampLookupIdsInDomain@@YAJPEAXKPEAKPEAPEAU_UNICODE_STRING@@PEAPEAW4_SID_NAME_USE@@@Z`
- size: `697`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, struct _UNICODE_STRING **@<r9>, enum _SID_NAME_USE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000f5c0`

## callees

- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ad50`
- `0x180014a50`
- `0x180014a90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af82`
- `RPCRT4!NdrClientCall3` at `0x18000aeb5`
- `RPCRT4!NdrClientCall3` at `0x18000aeb5`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000aef8`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000aef8`

## pseudocode

```c
__int64 __fastcall SampLookupIdsInDomain(
        void **a1,
        unsigned int a2,
        unsigned int *a3,
        struct _UNICODE_STRING **a4,
        enum _SID_NAME_USE **a5)
{
  CLIENT_CALL_RETURN v10; // rax
  int Pointer; // ebx
  void *v12; // rax
  void *v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-88h]
  void *v15; // [rsp+48h] [rbp-60h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+50h] [rbp-58h]
  __int128 v17; // [rsp+58h] [rbp-50h] BYREF
  __int128 v18; // [rsp+68h] [rbp-40h] BYREF

  v15 = 0;
  v17 = 0;
  v18 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a2);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a2 <= 0x3E8 )
      {
        if ( (unsigned __int8)SampIsValidClientHandle(a1, &v15) )
        {
          *((_QWORD *)&v18 + 1) = 0;
          *((_QWORD *)&v17 + 1) = 0;
          v16.Simple = 0;
          LODWORD(v14) = a2;
          v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x12u, 0, v15, v14, a3, &v18, &v17).Pointer;
          Pointer = (int)v10.Pointer;
          v16.Pointer = v10.Pointer;
          v12 = (void *)*((_QWORD *)&v18 + 1);
          *a4 = (struct _UNICODE_STRING *)*((_QWORD *)&v18 + 1);
          v13 = (void *)*((_QWORD *)&v17 + 1);
          if ( a5 )
          {
            *a5 = (enum _SID_NAME_USE *)*((_QWORD *)&v17 + 1);
          }
          else if ( *((_QWORD *)&v17 + 1) )
          {
            LocalFree(*((HLOCAL *)&v17 + 1));
            v13 = 0;
            *((_QWORD *)&v17 + 1) = 0;
            v12 = (void *)*((_QWORD *)&v18 + 1);
          }
          if ( Pointer && Pointer != 263 )
          {
            if ( a5 )
              *a5 = 0;
            if ( v13 )
            {
              LocalFree(v13);
              *((_QWORD *)&v17 + 1) = 0;
              v12 = (void *)*((_QWORD *)&v18 + 1);
            }
            *a4 = 0;
            if ( v12 )
            {
              LocalFree(v12);
              *((_QWORD *)&v18 + 1) = 0;
            }
          }
          if ( Pointer == -1073610749 )
            Pointer = -1073741816;
          if ( Pointer < 0 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                125,
                &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
                (unsigned int)Pointer);
          }
          else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
          }
          return (unsigned int)Pointer;
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
          return 3221225480LL;
        }
      }
      else
      {
        return 3221225626LL;
      }
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    *a4 = 0;
    if ( a5 )
      *a5 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ad50  mov     rax, rsp
0x18000ad53  mov     [rax+20h], r9
0x18000ad57  push    rbx
0x18000ad58  push    r12
0x18000ad5a  push    r14
0x18000ad5c  push    r15
0x18000ad5e  sub     rsp, 88h
0x18000ad65  mov     r15, r9
0x18000ad68  mov     r12, r8
0x18000ad6b  mov     ebx, edx
0x18000ad6d  mov     r14, rcx
0x18000ad70  mov     qword ptr [rax-60h], 0
0x18000ad78  xorps   xmm0, xmm0
0x18000ad7b  movups  xmmword ptr [rax-50h], xmm0
0x18000ad7f  xorps   xmm1, xmm1
0x18000ad82  movups  xmmword ptr [rax-40h], xmm1
0x18000ad86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad8d  test    byte ptr [rcx+1Ch], 2
0x18000ad91  jz      short loc_18000ADB5
0x18000ad93  cmp     byte ptr [rcx+19h], 4
0x18000ad97  jb      short loc_18000ADB5
0x18000ad99  mov     edx, 78h ; 'x'
0x18000ad9e  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000ada2  mov     r9, r14
0x18000ada5  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000adac  mov     rcx, [rcx+10h]
0x18000adb0  call    WPP_SF_qD
0x18000adb5  test    ebx, ebx
0x18000adb7  jnz     short loc_18000AE03
0x18000adb9  mov     qword ptr [r15], 0
0x18000adc0  mov     rax, [rsp+0A8h+arg_20]
0x18000adc8  test    rax, rax
0x18000adcb  jz      short loc_18000ADD4
0x18000adcd  mov     qword ptr [rax], 0
0x18000add4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000addb  test    byte ptr [rcx+1Ch], 2
0x18000addf  jz      short loc_18000ADFC
0x18000ade1  cmp     byte ptr [rcx+19h], 4
0x18000ade5  jb      short loc_18000ADFC
0x18000ade7  mov     edx, 79h ; 'y'
0x18000adec  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000adf3  mov     rcx, [rcx+10h]
0x18000adf7  call    WPP_SF_
0x18000adfc  xor     eax, eax
0x18000adfe  jmp     loc_18000AFFA
0x18000ae03  test    r12, r12
0x18000ae06  jnz     short loc_18000AE12
0x18000ae08  mov     eax, 0C000000Dh
0x18000ae0d  jmp     loc_18000AFFA
0x18000ae12  cmp     ebx, 3E8h
0x18000ae18  jbe     short loc_18000AE24
0x18000ae1a  mov     eax, 0C000009Ah
0x18000ae1f  jmp     loc_18000AFFA
0x18000ae24  lea     rdx, [rsp+0A8h+var_60]; void **
0x18000ae29  mov     rcx, r14; void *
0x18000ae2c  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000ae31  test    al, al
0x18000ae33  jnz     short loc_18000AE6A
0x18000ae35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae3c  test    byte ptr [rcx+1Ch], 2
0x18000ae40  jz      short loc_18000AE60
0x18000ae42  cmp     byte ptr [rcx+19h], 2
0x18000ae46  jb      short loc_18000AE60
0x18000ae48  mov     edx, 7Ah ; 'z'
0x18000ae4d  mov     r9, r14
0x18000ae50  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000ae57  mov     rcx, [rcx+10h]
0x18000ae5b  call    WPP_SF_q
0x18000ae60  mov     eax, 0C0000008h
0x18000ae65  jmp     loc_18000AFFA
0x18000ae6a  mov     [rsp+0A8h+var_38], 0
0x18000ae73  mov     [rsp+0A8h+hMem], 0
0x18000ae7c  mov     [rsp+0A8h+var_58], 0
0x18000ae85  lea     rax, [rsp+0A8h+var_50]
0x18000ae8a  mov     [rsp+0A8h+var_70], rax
0x18000ae8f  lea     rax, [rsp+0A8h+var_40]
0x18000ae94  mov     [rsp+0A8h+var_78], rax
0x18000ae99  mov     [rsp+0A8h+var_80], r12
0x18000ae9e  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000aea2  mov     r9, [rsp+0A8h+var_60]
0x18000aea7  xor     r8d, r8d; pReturnValue
0x18000aeaa  lea     edx, [r8+12h]; nProcNum
0x18000aeae  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000aeb5  call    cs:__imp_NdrClientCall3
0x18000aebb  mov     rbx, rax
0x18000aebe  mov     [rsp+0A8h+var_58], rax
0x18000aec3  mov     [rsp+0A8h+var_68], eax
0x18000aec7  jmp     short loc_18000AF0C
0x18000aec9  mov     ebx, eax
0x18000aecb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aed2  test    byte ptr [rcx+1Ch], 2
0x18000aed6  jz      short loc_18000AEF6
0x18000aed8  cmp     byte ptr [rcx+19h], 3
0x18000aedc  jb      short loc_18000AEF6
0x18000aede  mov     r9d, eax
0x18000aee1  mov     edx, 7Bh ; '{'
0x18000aee6  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000aeed  mov     rcx, [rcx+10h]
0x18000aef1  call    WPP_SF_D
0x18000aef6  mov     ecx, ebx; Status
0x18000aef8  call    cs:__imp_I_RpcMapWin32Status
0x18000aefe  mov     ebx, eax
0x18000af00  mov     [rsp+0A8h+var_68], eax
0x18000af04  mov     r15, [rsp+0A8h+arg_18]
0x18000af0c  mov     rax, [rsp+0A8h+var_38]
0x18000af11  mov     [r15], rax
0x18000af14  mov     r14, [rsp+0A8h+arg_20]
0x18000af1c  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18000af21  test    r14, r14
0x18000af24  jz      short loc_18000AF2B
0x18000af26  mov     [r14], rcx
0x18000af29  jmp     short loc_18000AF42
0x18000af2b  test    rcx, rcx
0x18000af2e  jz      short loc_18000AF42
0x18000af30  call    cs:__imp_LocalFree
0x18000af36  xor     ecx, ecx; hMem
0x18000af38  mov     [rsp+0A8h+hMem], rcx
0x18000af3d  mov     rax, [rsp+0A8h+var_38]
0x18000af42  test    ebx, ebx
0x18000af44  jz      short loc_18000AF91
0x18000af46  cmp     ebx, 107h
0x18000af4c  jz      short loc_18000AF91
0x18000af4e  test    r14, r14
0x18000af51  jz      short loc_18000AF5A
0x18000af53  mov     qword ptr [r14], 0
0x18000af5a  test    rcx, rcx
0x18000af5d  jz      short loc_18000AF73
0x18000af5f  call    cs:__imp_LocalFree
0x18000af65  mov     [rsp+0A8h+hMem], 0
0x18000af6e  mov     rax, [rsp+0A8h+var_38]
0x18000af73  mov     qword ptr [r15], 0
0x18000af7a  test    rax, rax
0x18000af7d  jz      short loc_18000AF91
0x18000af7f  mov     rcx, rax; hMem
0x18000af82  call    cs:__imp_LocalFree
0x18000af88  mov     [rsp+0A8h+var_38], 0
0x18000af91  mov     eax, 0C0000008h
0x18000af96  cmp     ebx, 0C0020003h
0x18000af9c  cmovz   ebx, eax
0x18000af9f  test    ebx, ebx
0x18000afa1  js      short loc_18000AFCD
0x18000afa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afaa  test    byte ptr [rcx+1Ch], 2
0x18000afae  jz      short loc_18000AFF8
0x18000afb0  cmp     byte ptr [rcx+19h], 4
0x18000afb4  jb      short loc_18000AFF8
0x18000afb6  mov     edx, 7Ch ; '|'
0x18000afbb  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000afc2  mov     rcx, [rcx+10h]
0x18000afc6  call    WPP_SF_
0x18000afcb  jmp     short loc_18000AFF8
0x18000afcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afd4  test    byte ptr [rcx+1Ch], 2
0x18000afd8  jz      short loc_18000AFF8
0x18000afda  cmp     byte ptr [rcx+19h], 2
0x18000afde  jb      short loc_18000AFF8
0x18000afe0  mov     edx, 7Dh ; '}'
0x18000afe5  mov     r9d, ebx
0x18000afe8  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000afef  mov     rcx, [rcx+10h]
0x18000aff3  call    WPP_SF_D
0x18000aff8  mov     eax, ebx
0x18000affa  add     rsp, 88h
0x18000b001  pop     r15
0x18000b003  pop     r14
0x18000b005  pop     r12
0x18000b007  pop     rbx
0x18000b008  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
