# sub_1800EBFE4

- ea: `0x1800ebfe4`
- end: `0x1800ec394`
- name: `sub_1800EBFE4`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ece48`

## callees

- `0x18003f3a8`
- `0x18003f3b4`
- `0x18003f7c0`
- `0x1800ebfe4`
- `0x1800edb90`
- `0x1800ede6c`
- `0x18016f400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec13f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec13f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec357`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800ec15b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800ec15b`

## pseudocode

```c
__int64 __fastcall sub_1800EBFE4(
        __int64 a1,
        __int64 a2,
        int (__fastcall ***a3)(__int64, _QWORD, __int64 *, _QWORD, __int64 *),
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        _DWORD *a11)
{
  __int64 v11; // rsi
  __int64 v12; // r14
  int (__fastcall **v13)(__int64, _QWORD, __int64 *, _QWORD, __int64 *); // rax
  HRESULT v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdi
  int v19; // r12d
  unsigned int v20; // r15d
  int v21; // r8d
  int v22; // r9d
  unsigned __int128 v23; // rax
  __int64 v24; // rax
  unsigned __int16 v25; // bx
  int v27; // [rsp+0h] [rbp-91h]
  int v28; // [rsp+0h] [rbp-91h]
  int v29; // [rsp+8h] [rbp-89h]
  int v30; // [rsp+8h] [rbp-89h]
  __int64 v31; // [rsp+10h] [rbp-81h]
  __int64 v32; // [rsp+10h] [rbp-81h]
  __int64 v33; // [rsp+18h] [rbp-79h]
  __int64 v34; // [rsp+18h] [rbp-79h]
  __int64 v35; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 v37; // [rsp+60h] [rbp-31h] BYREF
  __int64 v38; // [rsp+68h] [rbp-29h] BYREF
  __int64 v39; // [rsp+70h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-19h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-11h] BYREF
  int v42; // [rsp+84h] [rbp-Dh] BYREF
  int v43; // [rsp+88h] [rbp-9h] BYREF
  IID rclsid; // [rsp+90h] [rbp-1h] BYREF

  v11 = a6;
  v12 = a5;
  if ( !a3 || !a5 || !a6 || !a11 )
    return 2147942487LL;
  v39 = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  *a11 = 0;
  v13 = *a3;
  v41 = 0;
  v38 = 0;
  pv = 0;
  if ( (*v13)(a1, a6, &qword_180180EE8, a3, &v39) >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v39 + 192LL))(a1, v11, &v41);
    if ( v14 < 0 )
      goto LABEL_38;
    v18 = 0;
    v19 = v11;
    v20 = 0;
    while ( 2 )
    {
      if ( v20 >= v41 )
      {
        *a11 = v19 - v11;
      }
      else
      {
        if ( v38 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v18);
          v38 = 0;
        }
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v39 + 200LL))(
                v18,
                v11,
                v20,
                v39,
                &v38);
        if ( v14 >= 0 )
        {
          rclsid = (IID)xmmword_180181AE0;
          v14 = (*(__int64 (__fastcall **)(__int64, __int64, IID *))(*(_QWORD *)v38 + 48LL))(v18, v11, &rclsid);
          if ( v14 >= 0 )
          {
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            v14 = StringFromCLSID(&rclsid, (LPOLESTR *)&pv);
            if ( v14 >= 0 )
            {
              v42 = 0;
              v43 = 0;
              v14 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64, int *))(*(_QWORD *)v38 + 64LL))(
                      v18,
                      v11,
                      &v42,
                      v38,
                      &v43);
              if ( v14 >= 0 )
              {
                if ( (int)sub_1800EDE6C(
                            v18,
                            v11,
                            (unsigned int)v11,
                            v12,
                            &v35,
                            &v36,
                            v27,
                            v29,
                            v31,
                            v33,
                            0x1000u,
                            (const uintptr_t *)L"\r\n"
                                                "     <bandwidthsharing type=\"%s\" bufferwindow=\"%d\" bitrate=\"%d\">\r\n",
                            (char)pv) >= 0 )
                {
                  v37 = 0;
                  if ( v18 )
                    j_j__o_free(v18, v11, v15, v18, v16, v17);
                  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v38 + 24LL))(
                          v18,
                          v11,
                          0,
                          v38,
                          &v37);
                  if ( v14 < 0 )
                    goto LABEL_38;
                  v23 = v37 * (unsigned __int128)2uLL;
                  if ( !is_mul_ok(v37, 2u) )
                    LODWORD(v23) = -1;
                  v24 = sub_18003F3A8(v18, v11, SDWORD2(v23), v23, v21, v22);
                  v18 = v24;
                  if ( !v24 )
                  {
                    v14 = -2147024882;
                    goto LABEL_38;
                  }
                  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, unsigned __int16 *))(*(_QWORD *)v38 + 24LL))(
                          v24,
                          v11,
                          v24,
                          v38,
                          &v37);
                  if ( v14 >= 0 )
                  {
                    v25 = 0;
                    v11 = 1;
                    while ( v25 < v37 )
                    {
                      if ( (int)sub_1800EDE6C(
                                  v18,
                                  1,
                                  (unsigned int)v36,
                                  v35,
                                  &v35,
                                  &v36,
                                  v28,
                                  v30,
                                  v32,
                                  v34,
                                  0x1000u,
                                  (const uintptr_t *)L"\r\n      <stream number=\"%d\"/>\r\n",
                                  *(_WORD *)(v18 + 2LL * v25)) < 0 )
                        goto LABEL_32;
                      ++v25;
                    }
                    v14 = sub_1800EDB90(
                            v18,
                            1,
                            v36,
                            v35,
                            (unsigned int)L"\r\n     </bandwidthsharing>\r\n",
                            (unsigned int)&v35,
                            v28,
                            v30,
                            v32,
                            v34,
                            (__int64)&v36,
                            4096);
                    if ( v14 >= 0 )
                    {
                      v12 = v35;
                      ++v20;
                      v11 = (unsigned int)v36;
                      continue;
                    }
LABEL_32:
                    v14 = -1072887855;
                  }
LABEL_37:
                  j_j__o_free(v18, v11, v15, v18, v16, v17);
                  goto LABEL_38;
                }
                v14 = -1072887855;
              }
            }
          }
        }
      }
      break;
    }
    if ( !v18 )
      goto LABEL_38;
    goto LABEL_37;
  }
  v14 = 0;
LABEL_38:
  if ( v38 )
  {
    (*(void (**)(void))(*(_QWORD *)v38 + 16LL))();
    v38 = 0;
  }
  if ( v39 )
  {
    (*(void (**)(void))(*(_QWORD *)v39 + 16LL))();
    v39 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800ebfe4  mov     [rsp-8+arg_0], rbx
0x1800ebfe9  push    rbp
0x1800ebfea  push    rsi
0x1800ebfeb  push    rdi
0x1800ebfec  push    r12
0x1800ebfee  push    r13
0x1800ebff0  push    r14
0x1800ebff2  push    r15
0x1800ebff4  lea     rbp, [rsp-1Fh]
0x1800ebff9  sub     rsp, 0B0h
0x1800ec000  mov     rax, cs:__security_cookie
0x1800ec007  xor     rax, rsp
0x1800ec00a  mov     [rbp+4Fh+var_40], rax
0x1800ec00e  mov     r13, [rbp+4Fh+arg_20]
0x1800ec012  mov     esi, r9d
0x1800ec015  mov     r9, rdx
0x1800ec018  mov     r14, r8
0x1800ec01b  test    rdx, rdx
0x1800ec01e  jz      loc_1800EC367
0x1800ec024  test    r8, r8
0x1800ec027  jz      loc_1800EC367
0x1800ec02d  test    esi, esi
0x1800ec02f  jz      loc_1800EC367
0x1800ec035  test    r13, r13
0x1800ec038  jz      loc_1800EC367
0x1800ec03e  xor     eax, eax
0x1800ec040  mov     [rbp+4Fh+var_70], 0
0x1800ec048  mov     [rbp+4Fh+var_80], ax
0x1800ec04c  lea     r8, [rbp+4Fh+var_70]
0x1800ec050  mov     [rbp+4Fh+var_90], rax
0x1800ec054  mov     rcx, r9
0x1800ec057  mov     [rbp+4Fh+var_88], rax
0x1800ec05b  mov     [r13+0], eax
0x1800ec05f  mov     rax, [rdx]
0x1800ec062  lea     rdx, qword_180180EE8
0x1800ec069  mov     [rbp+4Fh+var_60], 0
0x1800ec070  mov     [rbp+4Fh+var_78], 0
0x1800ec078  mov     [rbp+4Fh+pv], 0
0x1800ec080  mov     rax, [rax]
0x1800ec083  call    cs:__guard_dispatch_icall_fptr
0x1800ec089  test    eax, eax
0x1800ec08b  jns     short loc_1800EC094
0x1800ec08d  xor     ebx, ebx
0x1800ec08f  jmp     loc_1800EC312
0x1800ec094  mov     rcx, [rbp+4Fh+var_70]
0x1800ec098  lea     rdx, [rbp+4Fh+var_60]
0x1800ec09c  mov     rax, [rcx]
0x1800ec09f  mov     rax, [rax+0C0h]
0x1800ec0a6  call    cs:__guard_dispatch_icall_fptr
0x1800ec0ac  mov     ebx, eax
0x1800ec0ae  test    eax, eax
0x1800ec0b0  js      loc_1800EC312
0x1800ec0b6  xor     edi, edi
0x1800ec0b8  mov     r12d, esi
0x1800ec0bb  xor     r15d, r15d
0x1800ec0be  cmp     r15d, [rbp+4Fh+var_60]
0x1800ec0c2  jnb     loc_1800EC2FE
0x1800ec0c8  mov     rcx, [rbp+4Fh+var_78]
0x1800ec0cc  test    rcx, rcx
0x1800ec0cf  jz      short loc_1800EC0E6
0x1800ec0d1  mov     rax, [rcx]
0x1800ec0d4  mov     rax, [rax+10h]
0x1800ec0d8  call    cs:__guard_dispatch_icall_fptr
0x1800ec0de  mov     [rbp+4Fh+var_78], 0
0x1800ec0e6  mov     rcx, [rbp+4Fh+var_70]
0x1800ec0ea  lea     r8, [rbp+4Fh+var_78]
0x1800ec0ee  mov     edx, r15d
0x1800ec0f1  mov     rax, [rcx]
0x1800ec0f4  mov     rax, [rax+0C8h]
0x1800ec0fb  call    cs:__guard_dispatch_icall_fptr
0x1800ec101  mov     ebx, eax
0x1800ec103  test    eax, eax
0x1800ec105  js      loc_1800EC305
0x1800ec10b  movups  xmm0, cs:xmmword_180181AE0
0x1800ec112  mov     rcx, [rbp+4Fh+var_78]
0x1800ec116  lea     rdx, [rbp+4Fh+rclsid]
0x1800ec11a  movdqu  xmmword ptr [rbp+4Fh+rclsid.Data1], xmm0
0x1800ec11f  mov     rax, [rcx]
0x1800ec122  mov     rax, [rax+30h]
0x1800ec126  call    cs:__guard_dispatch_icall_fptr
0x1800ec12c  mov     ebx, eax
0x1800ec12e  test    eax, eax
0x1800ec130  js      loc_1800EC305
0x1800ec136  mov     rcx, [rbp+4Fh+pv]; pv
0x1800ec13a  test    rcx, rcx
0x1800ec13d  jz      short loc_1800EC153
0x1800ec13f  call    cs:CoTaskMemFree
0x1800ec146  nop     dword ptr [rax+rax+00h]
0x1800ec14b  mov     [rbp+4Fh+pv], 0
0x1800ec153  lea     rdx, [rbp+4Fh+pv]; lplpsz
0x1800ec157  lea     rcx, [rbp+4Fh+rclsid]; rclsid
0x1800ec15b  call    cs:StringFromCLSID
0x1800ec162  nop     dword ptr [rax+rax+00h]
0x1800ec167  mov     ebx, eax
0x1800ec169  test    eax, eax
0x1800ec16b  js      loc_1800EC305
0x1800ec171  mov     rcx, [rbp+4Fh+var_78]
0x1800ec175  lea     r8, [rbp+4Fh+var_58]
0x1800ec179  mov     [rbp+4Fh+var_5C], 0
0x1800ec180  lea     rdx, [rbp+4Fh+var_5C]
0x1800ec184  mov     [rbp+4Fh+var_58], 0
0x1800ec18b  mov     rax, [rcx]
0x1800ec18e  mov     rax, [rax+40h]
0x1800ec192  call    cs:__guard_dispatch_icall_fptr
0x1800ec198  mov     ebx, eax
0x1800ec19a  test    eax, eax
0x1800ec19c  js      loc_1800EC305
0x1800ec1a2  mov     eax, [rbp+4Fh+var_5C]
0x1800ec1a5  lea     r9, [rbp+4Fh+var_88]
0x1800ec1a9  mov     [rsp+0E0h+var_A0], eax
0x1800ec1ad  lea     r8, [rbp+4Fh+var_90]
0x1800ec1b1  mov     eax, [rbp+4Fh+var_58]
0x1800ec1b4  mov     rcx, r14
0x1800ec1b7  mov     [rsp+0E0h+var_A8], eax
0x1800ec1bb  mov     rax, [rbp+4Fh+pv]
0x1800ec1bf  mov     [rsp+0E0h+var_B0], rax
0x1800ec1c4  lea     rax, aBandwidthshari; "\r\n     <bandwidthsharing type=\"%s\" "...
0x1800ec1cb  mov     [rsp+0E0h+var_B8], rax
0x1800ec1d0  mov     edx, esi
0x1800ec1d2  mov     dword ptr [rsp+0E0h+var_C0], 1000h
0x1800ec1da  call    sub_1800EDE6C
0x1800ec1df  test    eax, eax
0x1800ec1e1  js      loc_1800EC2F7
0x1800ec1e7  xor     eax, eax
0x1800ec1e9  mov     [rbp+4Fh+var_80], ax
0x1800ec1ed  test    rdi, rdi
0x1800ec1f0  jz      short loc_1800EC1FA
0x1800ec1f2  mov     rcx, rdi
0x1800ec1f5  call    j_j__o_free
0x1800ec1fa  mov     rcx, [rbp+4Fh+var_78]
0x1800ec1fe  lea     r8, [rbp+4Fh+var_80]
0x1800ec202  xor     edx, edx
0x1800ec204  mov     rax, [rcx]
0x1800ec207  mov     rax, [rax+18h]
0x1800ec20b  call    cs:__guard_dispatch_icall_fptr
0x1800ec211  mov     ebx, eax
0x1800ec213  test    eax, eax
0x1800ec215  js      loc_1800EC312
0x1800ec21b  movzx   ecx, [rbp+4Fh+var_80]
0x1800ec21f  mov     eax, 2
0x1800ec224  mul     rcx
0x1800ec227  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ec22e  cmovb   rax, rcx
0x1800ec232  mov     rcx, rax
0x1800ec235  call    sub_18003F3A8
0x1800ec23a  mov     rdi, rax; StackCookie
0x1800ec23d  test    rax, rax
0x1800ec240  jz      loc_1800EC2F0
0x1800ec246  mov     rcx, [rbp+4Fh+var_78]
0x1800ec24a  lea     r8, [rbp+4Fh+var_80]
0x1800ec24e  mov     rdx, rdi
0x1800ec251  mov     rax, [rcx]
0x1800ec254  mov     rax, [rax+18h]
0x1800ec258  call    cs:__guard_dispatch_icall_fptr
0x1800ec25e  mov     ebx, eax
0x1800ec260  test    eax, eax
0x1800ec262  js      loc_1800EC30A
0x1800ec268  xor     ebx, ebx
0x1800ec26a  mov     r14d, 1000h
0x1800ec270  lea     esi, [rbx+1]
0x1800ec273  mov     eax, dword ptr [rbp+4Fh+var_88]
0x1800ec276  mov     rcx, [rbp+4Fh+var_90]
0x1800ec27a  mov     edx, eax
0x1800ec27c  cmp     bx, [rbp+4Fh+var_80]
0x1800ec280  jnb     short loc_1800EC2B6
0x1800ec282  movzx   eax, bx
0x1800ec285  lea     r9, [rbp+4Fh+var_88]
0x1800ec289  movzx   r8d, word ptr [rdi+rax*2]
0x1800ec28e  lea     rax, aStreamNumberD; "\r\n      <stream number=\"%d\"/>\r\n"
0x1800ec295  mov     dword ptr [rsp+0E0h+var_B0], r8d
0x1800ec29a  lea     r8, [rbp+4Fh+var_90]
0x1800ec29e  mov     [rsp+0E0h+var_B8], rax
0x1800ec2a3  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800ec2a8  call    sub_1800EDE6C
0x1800ec2ad  test    eax, eax
0x1800ec2af  js      short loc_1800EC2E9
0x1800ec2b1  add     bx, si
0x1800ec2b4  jmp     short loc_1800EC273
0x1800ec2b6  lea     rax, [rbp+4Fh+var_88]
0x1800ec2ba  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x1800ec2bf  lea     r9, [rbp+4Fh+var_90]
0x1800ec2c3  mov     [rsp+0E0h+var_C0], rax
0x1800ec2c8  lea     r8, aBandwidthshari_0; "\r\n     </bandwidthsharing>\r\n"
0x1800ec2cf  call    sub_1800EDB90
0x1800ec2d4  mov     ebx, eax
0x1800ec2d6  test    eax, eax
0x1800ec2d8  js      short loc_1800EC2E9
0x1800ec2da  mov     r14, [rbp+4Fh+var_90]
0x1800ec2de  inc     r15d
0x1800ec2e1  mov     esi, dword ptr [rbp+4Fh+var_88]
0x1800ec2e4  jmp     loc_1800EC0BE
0x1800ec2e9  mov     ebx, 0C00D07D1h
0x1800ec2ee  jmp     short loc_1800EC30A
0x1800ec2f0  mov     ebx, 8007000Eh
0x1800ec2f5  jmp     short loc_1800EC312
0x1800ec2f7  mov     ebx, 0C00D07D1h
0x1800ec2fc  jmp     short loc_1800EC305
0x1800ec2fe  sub     r12d, esi
0x1800ec301  mov     [r13+0], r12d
0x1800ec305  test    rdi, rdi
0x1800ec308  jz      short loc_1800EC312
0x1800ec30a  mov     rcx, rdi
0x1800ec30d  call    j_j__o_free
0x1800ec312  mov     rcx, [rbp+4Fh+var_78]
0x1800ec316  test    rcx, rcx
0x1800ec319  jz      short loc_1800EC330
0x1800ec31b  mov     rax, [rcx]
0x1800ec31e  mov     rax, [rax+10h]
0x1800ec322  call    cs:__guard_dispatch_icall_fptr
0x1800ec328  mov     [rbp+4Fh+var_78], 0
0x1800ec330  mov     rcx, [rbp+4Fh+var_70]
0x1800ec334  test    rcx, rcx
0x1800ec337  jz      short loc_1800EC34E
0x1800ec339  mov     rax, [rcx]
0x1800ec33c  mov     rax, [rax+10h]
0x1800ec340  call    cs:__guard_dispatch_icall_fptr
0x1800ec346  mov     [rbp+4Fh+var_70], 0
0x1800ec34e  mov     rcx, [rbp+4Fh+pv]; pv
0x1800ec352  test    rcx, rcx
0x1800ec355  jz      short loc_1800EC363
0x1800ec357  call    cs:CoTaskMemFree
0x1800ec35e  nop     dword ptr [rax+rax+00h]
0x1800ec363  mov     eax, ebx
0x1800ec365  jmp     short loc_1800EC36C
0x1800ec367  mov     eax, 80070057h
0x1800ec36c  mov     rcx, [rbp+4Fh+var_40]
0x1800ec370  xor     rcx, rsp
0x1800ec373  call    __security_check_cookie
0x1800ec378  mov     rbx, [rsp+0E0h+arg_0]
0x1800ec380  add     rsp, 0B0h
0x1800ec387  pop     r15
0x1800ec389  pop     r14
0x1800ec38b  pop     r13
0x1800ec38d  pop     r12
0x1800ec38f  pop     rdi
0x1800ec390  pop     rsi
0x1800ec391  pop     rbp
0x1800ec392  retn
```
