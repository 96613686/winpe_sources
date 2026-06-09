# InitializeWarmupRequest(WARMUP_REQUEST *,IHttpContext *)

- ea: `0x180004204`
- end: `0x180004477`
- name: `?InitializeWarmupRequest@@YAJPEAUWARMUP_REQUEST@@PEAVIHttpContext@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(struct WARMUP_REQUEST *, struct IHttpContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002db8`
- `0x180004bc0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180004118`
- `0x180004204`
- `0x180004fb6`
- `0x180004fe0`
- `0x180006010`

## import_xrefs

- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180004305`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180004305`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800042ed`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800043cb`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800042ed`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800043cb`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000423a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004244`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000423a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004244`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004397`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004397`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042d5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000436d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004384`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042d5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000436d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004384`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042a1`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180004339`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180004339`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000443d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004447`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000443d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004447`

## pseudocode

```c
__int64 __fastcall InitializeWarmupRequest(struct WARMUP_REQUEST *a1, struct IHttpContext *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // ebx
  char *v8; // r15
  __int16 v9; // ax
  __int64 v10; // rax
  unsigned int v12; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v13[48]; // [rsp+38h] [rbp-41h] BYREF
  int v14; // [rsp+68h] [rbp-11h]
  _BYTE v15[32]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v16; // [rsp+90h] [rbp+17h]
  unsigned __int16 v17; // [rsp+A0h] [rbp+27h]

  STRA::STRA((STRA *)v15);
  STRA::STRA((STRA *)v13);
  v4 = *(_QWORD *)a2;
  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v4 + 24))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  memset_0((void *)v6, 0, 0x360u);
  *(_QWORD *)(v6 + 24) = (unsigned __int64)*(unsigned int *)a1 << 32;
  v7 = STRU::Copy((struct WARMUP_REQUEST *)((char *)a1 + 176), L"http://");
  if ( v7 >= 0 )
  {
    v7 = STRU::Append((struct WARMUP_REQUEST *)((char *)a1 + 176), *((const unsigned __int16 **)a1 + 19));
    if ( v7 >= 0 )
    {
      v7 = STRU::Append((struct WARMUP_REQUEST *)((char *)a1 + 176), L":80");
      if ( v7 >= 0 )
      {
        v7 = STRA::CopyW((STRA *)v13, *((const unsigned __int16 **)a1 + 5));
        if ( v7 >= 0 )
        {
          STRA::AppendW((STRA *)v13, *((const unsigned __int16 **)a1 + 12));
          v12 = v14 + 1;
          if ( (unsigned int)(v14 + 1) <= 0x7FFF )
          {
            v8 = (char *)operator new((unsigned int)(v14 + 1));
            v7 = STRA::CopyToBuffer((STRA *)v13, v8, &v12);
            if ( v7 < 0 )
            {
              if ( v8 )
                operator delete(v8);
            }
            else
            {
              *(_QWORD *)(v6 + 56) = v8;
              if ( v12 )
                v9 = v12 - 1;
              else
                v9 = 0;
              *(_WORD *)(v6 + 42) = v9;
              v7 = STRU::Append((struct WARMUP_REQUEST *)((char *)a1 + 176), *((const unsigned __int16 **)a1 + 5));
              if ( v7 >= 0 )
              {
                v7 = STRU::Append((struct WARMUP_REQUEST *)((char *)a1 + 176), *((const unsigned __int16 **)a1 + 12));
                if ( v7 >= 0 )
                {
                  STRU::SyncWithBuffer((struct WARMUP_REQUEST *)((char *)a1 + 176));
                  v7 = InitializeCookedUrl((struct WARMUP_REQUEST *)((char *)a1 + 176), (struct _HTTP_REQUEST_V2 *)v6);
                  if ( v7 >= 0 )
                  {
                    *(_DWORD *)(v6 + 36) = 4;
                    *(_DWORD *)(v6 + 32) = 65537;
                    v7 = STRA::CopyW((STRA *)v15, *((const unsigned __int16 **)a1 + 19));
                    if ( v7 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
                      v7 = (*(__int64 (__fastcall **)(__int64, const char *, __int64, _QWORD, int))(*(_QWORD *)v10 + 40LL))(
                             v10,
                             "Host",
                             v16,
                             v17,
                             1);
                      if ( v7 >= 0 )
                      {
                        *(_QWORD *)(v6 + 104) = &g_WarmupRemoteAddr;
                        *(_QWORD *)(v6 + 112) = &g_WarmupLocalAddr;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            v7 = -2147024362;
          }
        }
      }
    }
  }
  STRA::~STRA((STRA *)v13);
  STRA::~STRA((STRA *)v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004204  mov     [rsp-8+arg_10], rbx
0x180004209  mov     [rsp-8+arg_18], rsi
0x18000420e  push    rbp
0x18000420f  push    rdi
0x180004210  push    r12
0x180004212  push    r14
0x180004214  push    r15
0x180004216  lea     rbp, [rsp-37h]
0x18000421b  sub     rsp, 0B0h
0x180004222  mov     rax, cs:__security_cookie
0x180004229  xor     rax, rsp
0x18000422c  mov     [rbp+57h+var_28], rax
0x180004230  mov     rsi, rcx
0x180004233  mov     r12, rdx
0x180004236  lea     rcx, [rbp+57h+var_60]
0x18000423a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180004240  lea     rcx, [rbp+57h+var_98]
0x180004244  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000424a  mov     rax, [r12]
0x18000424e  mov     rcx, r12
0x180004251  mov     [rbp+57h+var_A0], 0
0x180004258  mov     rax, [rax+18h]
0x18000425c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004261  mov     rdx, rax
0x180004264  mov     rcx, [rax]
0x180004267  mov     rax, [rcx+8]
0x18000426b  mov     rcx, rdx
0x18000426e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004273  xor     edx, edx; Val
0x180004275  mov     r8d, 360h; Size
0x18000427b  mov     rcx, rax; void *
0x18000427e  mov     rdi, rax
0x180004281  call    memset_0
0x180004286  mov     ecx, [rsi]
0x180004288  lea     r14, [rsi+0B0h]
0x18000428f  shl     rcx, 20h
0x180004293  lea     rdx, aHttp; "http://"
0x18000429a  mov     [rdi+18h], rcx
0x18000429e  mov     rcx, r14
0x1800042a1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800042a7  mov     ebx, eax
0x1800042a9  test    eax, eax
0x1800042ab  js      loc_180004439
0x1800042b1  mov     rdx, [rsi+98h]
0x1800042b8  mov     rcx, r14
0x1800042bb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800042c1  mov     ebx, eax
0x1800042c3  test    eax, eax
0x1800042c5  js      loc_180004439
0x1800042cb  lea     rdx, a80; ":80"
0x1800042d2  mov     rcx, r14
0x1800042d5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800042db  mov     ebx, eax
0x1800042dd  test    eax, eax
0x1800042df  js      loc_180004439
0x1800042e5  mov     rdx, [rsi+28h]
0x1800042e9  lea     rcx, [rbp+57h+var_98]
0x1800042ed  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800042f3  mov     ebx, eax
0x1800042f5  test    eax, eax
0x1800042f7  js      loc_180004439
0x1800042fd  mov     rdx, [rsi+60h]
0x180004301  lea     rcx, [rbp+57h+var_98]
0x180004305  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x18000430b  mov     eax, [rbp+57h+var_68]
0x18000430e  inc     eax
0x180004310  mov     [rbp+57h+var_A0], eax
0x180004313  cmp     eax, 7FFFh
0x180004318  jbe     short loc_180004324
0x18000431a  mov     ebx, 80070216h
0x18000431f  jmp     loc_180004439
0x180004324  mov     ecx, eax; Size
0x180004326  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000432b  lea     r8, [rbp+57h+var_A0]
0x18000432f  mov     rdx, rax
0x180004332  lea     rcx, [rbp+57h+var_98]
0x180004336  mov     r15, rax
0x180004339  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x18000433f  mov     ebx, eax
0x180004341  test    eax, eax
0x180004343  js      loc_18000442C
0x180004349  mov     [rdi+38h], r15
0x18000434d  mov     r15d, 1
0x180004353  mov     eax, [rbp+57h+var_A0]
0x180004356  test    eax, eax
0x180004358  jz      short loc_180004360
0x18000435a  sub     ax, r15w
0x18000435e  jmp     short loc_180004362
0x180004360  xor     eax, eax
0x180004362  mov     [rdi+2Ah], ax
0x180004366  mov     rcx, r14
0x180004369  mov     rdx, [rsi+28h]
0x18000436d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004373  mov     ebx, eax
0x180004375  test    eax, eax
0x180004377  js      loc_180004439
0x18000437d  mov     rdx, [rsi+60h]
0x180004381  mov     rcx, r14
0x180004384  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000438a  mov     ebx, eax
0x18000438c  test    eax, eax
0x18000438e  js      loc_180004439
0x180004394  mov     rcx, r14
0x180004397  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000439d  mov     rdx, rdi; struct _HTTP_REQUEST_V2 *
0x1800043a0  mov     rcx, r14; struct STRU *
0x1800043a3  call    ?InitializeCookedUrl@@YAJPEAVSTRU@@PEAU_HTTP_REQUEST_V2@@@Z; InitializeCookedUrl(STRU *,_HTTP_REQUEST_V2 *)
0x1800043a8  mov     ebx, eax
0x1800043aa  test    eax, eax
0x1800043ac  js      loc_180004439
0x1800043b2  mov     dword ptr [rdi+24h], 4
0x1800043b9  lea     rcx, [rbp+57h+var_60]
0x1800043bd  mov     dword ptr [rdi+20h], 10001h
0x1800043c4  mov     rdx, [rsi+98h]
0x1800043cb  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800043d1  mov     ebx, eax
0x1800043d3  test    eax, eax
0x1800043d5  js      short loc_180004439
0x1800043d7  mov     rax, [r12]
0x1800043db  mov     rcx, r12
0x1800043de  mov     rax, [rax+18h]
0x1800043e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e7  movzx   r9d, [rbp+57h+var_30]
0x1800043ec  lea     rdx, aHost; "Host"
0x1800043f3  mov     r8, [rbp+57h+var_40]
0x1800043f7  mov     r10, rax
0x1800043fa  mov     [rsp+0D0h+var_B0], r15d
0x1800043ff  mov     rcx, [rax]
0x180004402  mov     rax, [rcx+28h]
0x180004406  mov     rcx, r10
0x180004409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000440e  mov     ebx, eax
0x180004410  test    eax, eax
0x180004412  js      short loc_180004439
0x180004414  lea     rax, ?g_WarmupRemoteAddr@@3Usockaddr_storage@@A; sockaddr_storage g_WarmupRemoteAddr
0x18000441b  mov     [rdi+68h], rax
0x18000441f  lea     rax, ?g_WarmupLocalAddr@@3Usockaddr_storage@@A; sockaddr_storage g_WarmupLocalAddr
0x180004426  mov     [rdi+70h], rax
0x18000442a  jmp     short loc_180004439
0x18000442c  test    r15, r15
0x18000442f  jz      short loc_180004439
0x180004431  mov     rcx, r15; Block
0x180004434  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004439  lea     rcx, [rbp+57h+var_98]
0x18000443d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004443  lea     rcx, [rbp+57h+var_60]
0x180004447  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000444d  mov     eax, ebx
0x18000444f  mov     rcx, [rbp+57h+var_28]
0x180004453  xor     rcx, rsp; StackCookie
0x180004456  call    __security_check_cookie
0x18000445b  lea     r11, [rsp+0D0h+var_20]
0x180004463  mov     rbx, [r11+40h]
0x180004467  mov     rsi, [r11+48h]
0x18000446b  mov     rsp, r11
0x18000446e  pop     r15
0x180004470  pop     r14
0x180004472  pop     r12
0x180004474  pop     rdi
0x180004475  pop     rbp
0x180004476  retn
```
